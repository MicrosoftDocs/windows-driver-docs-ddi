---
UID: NC:wdfdevice.EVT_WDF_IO_IN_CALLER_CONTEXT
title: EVT_WDF_IO_IN_CALLER_CONTEXT
author: windows-driver-content
description: A driver's EvtIoInCallerContext event callback function preprocesses an I/O request before the framework places it into an I/O queue.
old-location: wdf\evtioincallercontext.htm
old-project: wdf
ms.assetid: b8bcea29-e404-490e-9d0c-02c96a5690ab
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_027a6221-e735-4a5c-a378-d9d9236f21ae.xml, EVT_WDF_IO_IN_CALLER_CONTEXT, EvtIoInCallerContext, EvtIoInCallerContext callback function, kmdf.evtioincallercontext, wdf.evtioincallercontext, wdfdevice/EvtIoInCallerContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtIoInCallerContext
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_IO_IN_CALLER_CONTEXT callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtIoInCallerContext</i> event callback function preprocesses an I/O request before the framework places it into an I/O queue.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Request [in]

A handle to a framework request object.


## -returns



None




## -remarks



The framework calls a driver's <i>EvtIoInCallerContext</i> callback function so that the driver can examine each I/O request, and possibly perform preliminary processing on the request, before the framework places it in an I/O queue. To register an <i>EvtIoInCallerContext</i> callback function for a device, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546119">WdfDeviceInitSetIoInCallerContextCallback</a>. 

If a driver registers an <i>EvtIoInCallerContext</i> callback function for a device, the framework calls the callback function each time it receives an I/O request for the device. The callback function is called in the thread context of the process that sent the I/O request to the driver. This process is either the next-higher level driver or, if the driver is at the top of the driver stack, a user-mode application. 

This callback function's primary purpose is to enable framework-based drivers to support the buffer-access method that is called <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">neither buffered nor direct I/O</a>. For this buffer-access method, the driver must access received buffers in the originator's process context.

After the callback function has obtained a request's buffers, it can store buffer addresses or handles in the request object's context storage. (The driver sets the size of the request object's context storage area by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff546786">WdfDeviceInitSetRequestAttributes</a>.)

Because the request does not yet belong to an I/O queue, the framework does not lock or synchronize the request. The driver is responsible for any synchronization that might be necessary. For more information about synchronization, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.

After the callback function has finished preprocessing the request, it must either queue it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545945">WdfDeviceEnqueueRequest</a> or complete it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> (if an error is detected).

For more information about the <i>EvtIoInCallerContext</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Intercepting an I/O Request before it is Queued</a> and <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

If a driver has configured an I/O queue to support <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guaranteed forward progress</a>, the framework might not call the driver's <i>EvtIoInCallerContext</i> callback function during low-memory situations. If all of the framework's reserved request objects are in use, the framework postpones processing the I/O request until a reserved request object is available. In this situation, the framework cannot call the <i>EvtIoInCallerContext</i> callback function for the postponed I/O request because, when a reserved request object becomes available, the framework will no longer be running in the thread context of the process that sent the I/O request to the driver.

The <i>EvtIoInCallerContext</i> callback function is called at the IRQL of the calling thread. If the calling thread is from a user-mode application, the callback function is called at IRQL = PASSIVE_LEVEL. If the calling thread is from a higher-level kernel-mode driver, your driver's <i>EvtIoInCallerContext</i> callback function can be called at IRQL &lt;= DISPATCH_LEVEL if both the callback function and the higher-level driver are designed to pass the request at IRQL &lt;= DISPATCH_LEVEL.


#### Examples

To define an <i>EvtIoInCallerContext</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoInCallerContext</i> callback function that is named <i>MyIoInCallerContext</i>, use the <b>EVT_WDF_IO_IN_CALLER_CONTEXT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_IN_CALLER_CONTEXT  MyIoInCallerContext;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyIoInCallerContext  (
    WDFDEVICE  Device,
    WDFREQUEST  Request
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_IN_CALLER_CONTEXT</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_IN_CALLER_CONTEXT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a">EvtDeviceWdmIrpPreprocess</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_IN_CALLER_CONTEXT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

