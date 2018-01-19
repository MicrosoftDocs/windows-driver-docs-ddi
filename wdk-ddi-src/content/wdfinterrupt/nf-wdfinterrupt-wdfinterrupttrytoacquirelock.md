---
UID: NF:wdfinterrupt.WdfInterruptTryToAcquireLock
title: WdfInterruptTryToAcquireLock function
author: windows-driver-content
description: The WdfInterruptTryToAcquireLock method attempts to acquire an interrupt object's passive lock.
old-location: wdf\wdfinterrupttrytoacquirelock.htm
old-project: wdf
ms.assetid: 272165BE-3DF2-410C-B60A-31B48A3F3231
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfInterruptTryToAcquireLock
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
req.alt-api: WdfInterruptTryToAcquireLock
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptTryToAcquireLock function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

 The <b>WdfInterruptTryToAcquireLock</b> method attempts to acquire an interrupt object's passive lock. 



## -syntax

````
BOOLEAN WdfInterruptTryToAcquireLock(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters

### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns
<b>WdfInterruptTryToAcquireLock</b> returns TRUE if it successfully acquires the interrupt’s lock. Otherwise, the method returns FALSE.


## -remarks
Drivers that use <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a> call <b>WdfInterruptTryToAcquireLock</b> to start a code sequence that executes at IRQL = PASSIVE_LEVEL while holding the passive-level interrupt lock that the driver configured in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure.

<b>WdfInterruptTryToAcquireLock</b> attempts to acquire the lock and then returns immediately, whether it has acquired the lock or not. If <b>WdfInterruptTryToAcquireLock</b> does successfully acquire the lock, the framework calls <a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a> before returning so that normal kernel APCs are disabled.

For passive-level interrupt objects, drivers must call <b>WdfInterruptTryToAcquireLock</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>, when running in an arbitrary thread, such as a <a href="https://msdn.microsoft.com/5C311AF5-A67A-4F97-8605-1DD16C9D7839">queue object callback function</a>. For example, the driver might call <b>WdfInterruptTryToAcquireLock</b> from <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a>.  Doing so avoids the possibility of deadlock, as described in the Remarks section of <b>WdfInterruptAcquireLock</b>.

When running in  a non-arbitrary thread, such as a work item, the driver should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>.

When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>, the framework releases the interrupt lock.

The following code example shows how an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a> callback function, running in an arbitrary context, might call <b>WdfInterruptTryToAcquireLock</b> before performing interrupt-related work. If  the method returns FALSE, the driver queues a work item to perform the work in a non-arbitrary thread. The driver also supplies an <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function that calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a> before it performs the work.

 In this example, the driver has specified <a href="wdf.dispatching_methods_for_i_o_requests#sequential_dispatching#sequential_dispatching">sequential</a> dispatching for the queue.   If the driver specified <i>any other dispatching method</i> for the queue, the driver should use an additional manual queue to retain requests for processing in the work item.  Code comments describe where to add such support.


## -see-also
<dl>
<dt>
<a href="..\wdfsync\nf-wdfsync-wdfwaitlockacquire.md">WdfWaitLockAcquire</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547340">WdfInterruptAcquireLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547376">WdfInterruptReleaseLock</a>
</dt>
<dt>
<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a>
</dt>
<dt>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestrequeue.md">WdfRequestRequeue</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueueretrievenextrequest.md">WdfIoQueueRetrieveNextRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptTryToAcquireLock method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

