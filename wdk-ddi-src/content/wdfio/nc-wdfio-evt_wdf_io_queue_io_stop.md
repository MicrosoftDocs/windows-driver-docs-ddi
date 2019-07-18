---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_STOP
title: EVT_WDF_IO_QUEUE_IO_STOP (wdfio.h)
description: A driver's EvtIoStop event callback function completes, requeues, or suspends processing of a specified request because the request's I/O queue is being stopped.
old-location: wdf\evtiostop.htm
tech.root: wdf
ms.assetid: 71a789f1-4f10-44c3-8bd0-a0ea74ec28ab
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_b9df4689-1de5-4c08-b2a2-c9f126a7d0bc.xml, EVT_WDF_IO_QUEUE_IO_STOP, EVT_WDF_IO_QUEUE_IO_STOP callback, EvtIoStop, EvtIoStop callback function, kmdf.evtiostop, wdf.evtiostop, wdfio/EvtIoStop
ms.topic: callback
f1_keywords:
 - "wdfio/EvtIoStop"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfio.h
api_name:
- EvtIoStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_IO_STOP callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoStop</i> event callback function completes, requeues, or suspends processing of a specified request because the request's I/O queue is being stopped.


## -parameters




### -param Queue [in]

A handle to the framework queue object that is associated with the I/O request.


### -param Request [in]

A handle to a framework request object.


### -param ActionFlags [in]

A bitwise OR of one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ne-wdfrequest-_wdf_request_stop_action_flags">WDF_REQUEST_STOP_ACTION_FLAGS</a>-typed flags that identify the reason that the callback function is being called and whether the request is cancelable.


## -returns



None




## -remarks



A driver registers an <i>EvtIoStop</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver registers an <i>EvtIoStop</i> callback function for an I/O queue, the framework calls it when the queue's underlying device is leaving its working (D0) state. The framework calls the <i>EvtIoStop</i> callback function for every I/O request that the driver has not <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completed</a>, including requests that the driver <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-ownership">owns</a> and those that it has <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">forwarded</a> to an I/O target.

In  most cases, the <i>EvtIoStop</i> callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a>, or postpones further processing of the I/O request. 

Typically, the driver does one of the following:

<ul>
<li>
If the driver owns the I/O request, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> (if the request is cancelable)  and either calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequeststopacknowledge">WdfRequestStopAcknowledge</a> with a <i>Requeue</i> value of TRUE, or it calls  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> with a completion status value of STATUS_SUCCESS or STATUS_CANCELLED.

Before it can call <b>WdfRequest<i>Xxx</i></b> methods safely, the driver must make sure that its implementation of <i>EvtIoStop</i> has exclusive access to the request.   

In order to do that, the driver must synchronize access to the request to prevent other threads from manipulating the request concurrently.  The synchronization method you choose will depend on your driver's design.

For example, if the request is held in a shared context area, the <i>EvtIoStop</i> callback might acquire an internal driver lock, remove the request from the shared context, and then release the lock. At this point, the <i>EvtIoStop</i> callback owns the request and can safely complete or requeue the request.

Alternatively, the driver postpones further processing of the request and calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequeststopacknowledge">WdfRequestStopAcknowledge</a> with a <i>Requeue</i> value of FALSE.

</li>
<li>
If the driver has forwarded the I/O request to an I/O target, it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a> to attempt to cancel the request.

Or, if the driver has forwarded the I/O request to a lower-level driver in its own driver stack, and the framework calls the driver's <i>EvtIoStop</i> callback with an <i>ActionFlags</i> value of <b>WdfRequestStopActionSuspend</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequeststopacknowledge">WdfRequestStopAcknowledge</a> with a <i>Requeue</i> value of FALSE. Before doing so, the driver should verify that the following conditions are met:<ul>
<li>The lower driver stops processing all outstanding I/O requests in response to receiving a device set-power IRP (Dx). </li>
<li> The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function can  complete requests while the device is in a low-power state.</li>
</ul>


</li>
</ul>
A driver might choose to take no action in <i>EvtIoStop</i> for requests that are guaranteed to complete in a small amount of time.

   In this case, the framework waits until the specified request is complete before moving the device (or system) to a lower power state or removing the device. Potentially, this inaction can prevent a system from entering its hibernation state or another low system power state. In extreme cases, it can cause the system to crash with bugcheck code 9F.

If the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ne-wdfrequest-_wdf_request_stop_action_flags">WdfRequestStopRequestCancelable</a> flag is set in the <i>ActionFlags</i> parameter, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete (or cancel) the request or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequeststopacknowledge">WdfRequestStopAcknowledge</a> to requeue the request.

If the driver forwards an I/O request from one of its <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handlers</a>
and specifies the <b>WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET</b> flag in the request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure, the framework does not call the driver's <i>EvtIoStop</i> callback function for this request. However, if the driver forwards the same I/O request from another thread, the framework might call <i>EvtIoStop</i> for this request.

For more information about the <i>EvtIoStop</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">Using Power-Managed I/O Queues</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.


#### Examples

To define an <i>EvtIoStop</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoStop</i> callback function that is named <i>MyIoStop</i>, use the <b>EVT_WDF_IO_QUEUE_IO_STOP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_QUEUE_IO_STOP  MyIoStop;</pre>
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
 MyIoStop (
    WDFQUEUE  Queue,
    WDFREQUEST  Request,
    ULONG  ActionFlags
    )
..{...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_QUEUE_IO_STOP</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_STOP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_resume">EvtIoResume</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ne-wdfrequest-_wdf_request_stop_action_flags">WDF_REQUEST_STOP_ACTION_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequeststopacknowledge">WdfRequestStopAcknowledge</a>
 

 

