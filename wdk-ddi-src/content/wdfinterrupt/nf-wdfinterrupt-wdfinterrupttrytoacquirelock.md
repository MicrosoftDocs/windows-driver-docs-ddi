---
UID: NF:wdfinterrupt.WdfInterruptTryToAcquireLock
title: WdfInterruptTryToAcquireLock function
author: windows-driver-content
description: The WdfInterruptTryToAcquireLock method attempts to acquire an interrupt object's passive lock.
old-location: wdf\wdfinterrupttrytoacquirelock.htm
old-project: wdf
ms.assetid: 272165BE-3DF2-410C-B60A-31B48A3F3231
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfInterruptTryToAcquireLock, WdfInterruptTryToAcquireLock method, kmdf.wdfinterrupttrytoacquirelock, wdf.wdfinterrupttrytoacquirelock, wdfinterrupt/WdfInterruptTryToAcquireLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfInterruptTryToAcquireLock
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptTryToAcquireLock function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

 The <b>WdfInterruptTryToAcquireLock</b> method attempts to acquire an interrupt object's passive lock. 


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



<b>WdfInterruptTryToAcquireLock</b> returns TRUE if it successfully acquires the interrupt’s lock. Otherwise, the method returns FALSE.




## -remarks



Drivers that use <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a> call <b>WdfInterruptTryToAcquireLock</b> to start a code sequence that executes at IRQL = PASSIVE_LEVEL while holding the passive-level interrupt lock that the driver configured in the interrupt object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a> structure.

<b>WdfInterruptTryToAcquireLock</b> attempts to acquire the lock and then returns immediately, whether it has acquired the lock or not. If <b>WdfInterruptTryToAcquireLock</b> does successfully acquire the lock, the framework calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff552021">KeEnterCriticalRegion</a> before returning so that normal kernel APCs are disabled.

For passive-level interrupt objects, drivers must call <b>WdfInterruptTryToAcquireLock</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>, when running in an arbitrary thread, such as a <a href="https://msdn.microsoft.com/5C311AF5-A67A-4F97-8605-1DD16C9D7839">queue object callback function</a>. For example, the driver might call <b>WdfInterruptTryToAcquireLock</b> from <a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a>.  Doing so avoids the possibility of deadlock, as described in the Remarks section of <b>WdfInterruptAcquireLock</b>.

When running in  a non-arbitrary thread, such as a work item, the driver should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>.

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>, the framework releases the interrupt lock.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a> callback function, running in an arbitrary context, might call <b>WdfInterruptTryToAcquireLock</b> before performing interrupt-related work. If  the method returns FALSE, the driver queues a work item to perform the work in a non-arbitrary thread. The driver also supplies an <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function that calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a> before it performs the work.

 In this example, the driver has specified <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">sequential</a> dispatching for the queue.   If the driver specified <i>any other dispatching method</i> for the queue, the driver should use an additional manual queue to retain requests for processing in the work item.  Code comments describe where to add such support.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
VOID EvtIoRead(
  __in  WDFQUEUE Queue,
  __in  WDFREQUEST Request,
  __in  size_t Length
    )
{
    DEVICE_CONTEXT    devCtx;
    devCtx = GetDeviceContext(WdfIoQueueGetDevice(Queue));
    
    //
    // Do any pre-acquiring interrupt lock work here.
    //
   

    //
    // Check if we can acquire the lock.
    //
    if (WdfInterruptTryToAcquireLock(devCtx-&gt;InterruptObject) {
        ReadFunctionLocked(Request);
        WdfInterruptReleaseLock(devCtx-&gt;InterruptObject);
        //
        // Do any post-releasing interrupt lock work here.
        // For example: complete the request, and so on.
        //
        ReadFunctionFinish(Request); 
    }
    else {
        WORK_ITEM_CONTEXT ctx;

        ctx = GetWorkItemContext(ReadWorkItem);
        ctx-&gt;Request = Request;

        // If previous queue is non-sequential, call WdfRequestForwardToIoQueue 
        // to store request in an additional manual queue.

        WdfWorkItemEnqueue(ReadWorkItem);
    }
}


VOID
EvtReadWorkItemCallback(
    WDFWORKITEM WorkItem
    )
{
    WORK_ITEM_CONTEXT wiCtx;
    DEVICE_CONTEXT    devCtx;

    wiCtx = GetWorkItemContext(ReadWorkItem);
    devCtx = GetDeviceContext(WdfWorkItemGetParentObject(WorkItem));

    // If delivery queue is non-sequential, call WdfIoQueueRetrieveNextRequest 
    // to retrieve request that we stored in EvtIoRead.

    //
    // Acquire interrupt lock.
    //
    WdfInterruptAcquireLock(devCtx-&gt;InterruptObject);
    ReadFunctionLocked(wiCtx-&gt;Request);
    WdfInterruptReleaseLock(devCtx-&gt;InterruptObject);

    //
    // Do any post-releasing interrupt lock work here.
    // For example: complete the request, and so on.
    //
    ReadFunctionFinish(wiCtx-&gt;Request); 
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/1A473A08-EA23-4DFE-8B58-EBB4AC977891">EvtInterruptWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552347">WDF_INTERRUPT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975100">WdfIoQueueRetrieveNextRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550012">WdfRequestRequeue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551168">WdfWaitLockAcquire</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptTryToAcquireLock method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

