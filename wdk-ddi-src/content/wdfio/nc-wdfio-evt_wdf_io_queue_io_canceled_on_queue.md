---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE
title: EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE
author: windows-driver-content
description: A driver's EvtIoCanceledOnQueue event callback function informs the driver that it must complete an I/O request that the framework has removed from an I/O queue.
old-location: wdf\evtiocanceledonqueue.htm
tech.root: wdf
ms.assetid: 1b938ee8-a5f3-4a1e-9beb-231d88aa5848
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_24cf727b-3673-44a1-94a2-5308aa195827.xml, EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE, EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE callback, EvtIoCanceledOnQueue, EvtIoCanceledOnQueue callback function, kmdf.evtiocanceledonqueue, wdf.evtiocanceledonqueue, wdfio/EvtIoCanceledOnQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfio.h
api_name:
-	EvtIoCanceledOnQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoCanceledOnQueue</i> event callback function informs the driver that it must complete an I/O request that the framework has removed from an I/O queue.


## -parameters




### -param Queue [in]

A handle to an I/O queue object.


### -param Request [in]

A handle to a request object.


## -returns



None




## -remarks



A driver registers an <i>EvtIoCanceledOnQueue</i> callback function when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a> method. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver registers an <i>EvtIoCanceledOnQueue</i> callback function for an I/O queue, the framework calls the callback function in the following situations:

<ul>
<li>
A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a> receives an I/O request from an I/O queue, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550012">WdfRequestRequeue</a> to requeue the request to the I/O queue for which the <i>EvtIoCanceledOnQueue</i> callback function is registered, and the associated I/O operation is subsequently canceled.

</li>
<li>
The driver's <a href="https://msdn.microsoft.com/b8bcea29-e404-490e-9d0c-02c96a5690ab">EvtIoInCallerContext</a> callback function receives an I/O request, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545945">WdfDeviceEnqueueRequest</a> to pass the request back to the framework, the framework then places the request in the I/O queue for which the <i>EvtIoCanceledOnQueue</i> callback function is registered, and the associated I/O operation is subsequently canceled.

</li>
</ul>
After the framework calls the <i>EvtIoCanceledOnQueue</i> callback function, the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-ownership">owns</a> the request object and must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">complete</a> the request with an appropriate status code, either in <i>EvtIoCanceledOnQueue</i> or later.  When the framework calls <i>EvtIoCanceledOnQueue</i>, the request is still associated with the I/O queue, but the driver cannot requeue the request. The ownership of the request stays with the driver even if the driver does not complete the request in <i>EvtIoCanceledOnQueue</i>. If the driver completes the request after <i>EvtIoCanceledOnQueue</i> returns, it cannot call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>  and <a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">WdfIoQueueRetrieveFoundRequest</a> to reacquire ownership of the request because the driver already has ownership of the request.

Typically, in <i>EvtIoCanceledOnQueue</i>, the driver <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> with a completion status of STATUS_CANCELLED.

In some cases, the driver might have previously requeued an I/O request to a manual queue, perhaps to wait for information.  For example, in one of its <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handlers</a>, a driver might place an I/O request that is associated with a pending DMA transaction in a manual queue.  In this case, the driver attempts to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-dma-transactions">cancel the DMA transaction</a> in its <i>EvtIoCanceledOnQueue</i> callback. Depending on the results of the cancel operation, the driver completes the request with an appropriate status, either in <i>EvtIoCanceledOnQueue</i> or later.

The framework does not call the driver's <i>EvtIoCanceledOnQueue</i> callback function for I/O requests that the framework has never delivered to the driver.

The framework calls an <i>EvtIoCanceledOnQueue</i> callback function as soon as it determines that an I/O request has been canceled, regardless of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">dispatching method</a> that the driver has set for the I/O queue. Therefore, the framework can call an <i>EvtIoCanceledOnQueue</i> callback function for:

<ul>
<li>
A request in a queue that uses <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">sequential dispatching</a>, even if the driver currently owns another request from the queue.

</li>
<li>
A request in a queue for which the driver has set <a href="https://msdn.microsoft.com/aa8b64a7-eae9-444c-892f-841ca5a610cf">NumberOfPresentedRequests</a>, even if the driver currently owns the maximum number of requests.

</li>
</ul>
For more information about the <i>EvtIoCanceledOnQueue</i> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.

The <i>EvtIoCanceledOnQueue</i> callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.


#### Examples

To define an <i>EvtIoCanceledOnQueue</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

To define an <i>EvtIoCanceledOnQueue</i> callback function, you must first provide a function declaration that SDV and other verification tools require.  The following example is taken from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256155">PCMCIA Smart Card Driver</a> sample.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE PscrEvtIoCanceledOnQueue;</pre>
</td>
</tr>
</table></span></div>
In the <a href="http://go.microsoft.com/fwlink/p/?linkid=256155">PCMCIA Smart Card Driver</a> sample, the driver uses a manual queue to store pending smart card notification requests. The driver provides an <i>EvtIoCanceledOnQueue</i> callback function in which the driver clears the notification field and completes the request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
PscrEvtIoCanceledOnQueue(
    WDFQUEUE  Queue,
    WDFREQUEST  Request
    )

{
    PDEVICE_EXTENSION DeviceExtension;
    PSMARTCARD_EXTENSION smartcardExtension;

    DeviceExtension = GetDeviceExtension(WdfIoQueueGetDevice(Queue));
    smartcardExtension = (PSMARTCARD_EXTENSION) &amp;DeviceExtension-&gt;SmartcardExtension;

    //KdPrint(("Cancelled on queue 0x%x\n", WdfRequestWdmGetIrp(Request)));

    InterlockedExchangePointer(
                             &amp;(smartcardExtension-&gt;OsData-&gt;NotificationIrp),
                             NULL
                             );

    WdfRequestComplete(Request, STATUS_CANCELLED);
}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549958">WdfRequestForwardToIoQueue</a>
 

 

