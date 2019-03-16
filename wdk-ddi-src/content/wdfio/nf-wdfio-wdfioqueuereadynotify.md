---
UID: NF:wdfio.WdfIoQueueReadyNotify
title: WdfIoQueueReadyNotify function (wdfio.h)
description: The WdfIoQueueReadyNotify method registers (or deregisters) an event callback function that the framework calls each time a specified I/O queue that was previously empty receives one or more I/O requests.
old-location: wdf\wdfioqueuereadynotify.htm
tech.root: wdf
ms.assetid: 0d48dce1-252f-4dc2-85a8-6c25e99ce0ba
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_4816d999-fba0-46f6-8fbf-e1421d3d87e2.xml, WdfIoQueueReadyNotify, WdfIoQueueReadyNotify method, kmdf.wdfioqueuereadynotify, wdf.wdfioqueuereadynotify, wdfio/WdfIoQueueReadyNotify
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfIoQueueReadyNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueReadyNotify function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueReadyNotify</b> method registers (or deregisters) an event callback function that the framework calls each time a specified I/O queue that was previously empty receives one or more I/O requests.


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param QueueReady [in, optional]

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function, if the driver is registering for ready notification, or <b>NULL</b> if the driver is deregistering. 


### -param Context [in, optional]

An untyped pointer to driver-supplied context information that the framework passes to the <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function, if the driver is registering for ready notification, or <b>NULL</b> if the driver is deregistering. 


## -returns



<b>WdfIoQueueReadyNotify</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied an invalid handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
This value is returned if one of the following occurs:

<ul>
<li>
The <b>DispatchType</b> member of the specified I/O queue's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a> structure is not <b>WdfIoQueueDispatchManual</b>.

</li>
<li>
The driver had previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548452">WdfIoQueueReadyNotify</a> and registered an <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function. 

</li>
<li>
The driver is attempting to deregister its notification callback function, but a callback function is not registered or the driver has not called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548482">WdfIoQueueStop</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548489">WdfIoQueueStopSynchronously</a>.

</li>
</ul>
</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After a driver has called <b>WdfIoQueueReadyNotify</b> to register a <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function, the framework calls the callback function each time the specified queue's state changes from empty to non-empty. Specifically, the framework calls <i>EvtIoQueueState</i> when a request arrives on an empty queue, even if the driver still owns previously delivered requests from the queue that it has not yet completed. You can modify the IRQL at which the callback runs by specifying **ExecutionLevel** in [WDF_OBJECT_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes) at queue creation time. For more info, see the Remarks section of[*EVT_WDF_IO_QUEUE_STATE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_state).

The framework does not call <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> while the specified queue is stopped. When the queue starts, the framework calls <i>EvtIoQueueState</i> if the queue is non-empty.

Your driver can call <b>WdfIoQueueReadyNotify</b> only for I/O queues that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">manual dispatching</a> method. 

The <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function typically calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh975100">WdfIoQueueRetrieveNextRequest</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548470">WdfIoQueueRetrieveRequestByFileObject</a> in a loop to retrieve all of the requests that have arrived since the last time the callback function executed.

To stop the framework from calling the <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function, the driver must call <b>WdfIoQueueReadyNotify</b> again with the <i>QueueReady</i> parameter set to <b>NULL</b>. However, the driver must first call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548482">WdfIoQueueStop</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548489">WdfIoQueueStopSynchronously</a> to stop the I/O queue. The driver can subsequently call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548478">WdfIoQueueStart</a> to restart the queue.

When a driver calls <b>WdfIoQueueReadyNotify</b> to register a <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function, it is possible for the framework to call the callback function before <b>WdfIoQueueReadyNotify</b> returns.

For more information about the <b>WdfIoQueueReadyNotify</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>.


#### Examples

The following code example registers a driver's <b>EvtIoQueueReady</b> function, so that this function will be called when the specified I/O queue receives an I/O request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Status = WdfIoQueueReadyNotify(
                               ReadQueue,
                               EvtIoQueueReady,
                               myQueueContext
                               );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552359">WDF_IO_QUEUE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975100">WdfIoQueueRetrieveNextRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548470">WdfIoQueueRetrieveRequestByFileObject</a>
 

 

