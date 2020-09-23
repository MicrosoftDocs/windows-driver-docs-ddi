---
UID: NF:wdfrequest.WdfRequestForwardToParentDeviceIoQueue
title: WdfRequestForwardToParentDeviceIoQueue function (wdfrequest.h)
description: The WdfRequestForwardToParentDeviceIoQueue method requeues an I/O request from a child device's I/O queue to a specified I/O queue of the child's parent device.
old-location: wdf\wdfrequestforwardtoparentdeviceioqueue.htm
tech.root: wdf
ms.assetid: 81511d81-206c-420b-a956-42cf68b57fc4
ms.date: 02/26/2018
keywords: ["WdfRequestForwardToParentDeviceIoQueue function"]
ms.keywords: DFRequestObjectRef_0bfa4a8a-7b79-4256-84df-5bdabfff234b.xml, WdfRequestForwardToParentDeviceIoQueue, WdfRequestForwardToParentDeviceIoQueue method, kmdf.wdfrequestforwardtoparentdeviceioqueue, wdf.wdfrequestforwardtoparentdeviceioqueue, wdfrequest/WdfRequestForwardToParentDeviceIoQueue
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestForwardToParentDeviceIoQueue
 - wdfrequest/WdfRequestForwardToParentDeviceIoQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfRequestForwardToParentDeviceIoQueue
---

# WdfRequestForwardToParentDeviceIoQueue function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestForwardToParentDeviceIoQueue</b> method requeues an I/O request from a child device's I/O queue to a specified I/O queue of the child's parent device.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

### -param ParentDeviceQueue 

[in]
A handle to a framework queue object.

### -param ForwardOptions 

[in]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_forward_options">WDF_REQUEST_FORWARD_OPTIONS</a> structure.

## -returns

<b>WdfRequestForwardToParentDeviceIoQueue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the supplied WDF_REQUEST_FORWARD_OPTIONS structure is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A member of the supplied WDF_REQUEST_FORWARD_OPTIONS structure contains an invalid value.

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
The driver did not obtain the I/O request from an I/O queue.

</li>
<li>
The source and destination I/O queues are the same.

</li>
<li>
The specified I/O queue does not belong to the parent device.

</li>
<li>
The driver has enabled <a href="/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guaranted forward progress</a> and the specified I/O request is reserved for low-memory situations.

</li>
<li>
The driver did not call <a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent">WdfPdoInitAllowForwardingRequestToParent</a>.

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The specified I/O queue is not accepting new requests.

</td>
</tr>
</table>
 

This method might also return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.

## -remarks

Before a driver can call <b>WdfRequestForwardToParentDeviceIoQueue</b>, it must call <a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent">WdfPdoInitAllowForwardingRequestToParent</a>.

The driver must use the same <a href="/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">method to access data buffers</a> (buffered, direct, or neither) for both the parent device and the child device.

If your driver will call <b>WdfRequestForwardToParentDeviceIoQueue</b> to requeue an I/O request, the driver must not use the request object as the parent of other framework objects, such as timer objects or work item objects.

If your driver has called <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a> to specify <a href="/windows-hardware/drivers/wdf/framework-object-context-space">context space</a> for the <i>parent</i> device's request objects, the framework does not add this context space to request objects that the driver receives in a child device's queue. The driver can call <a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectallocatecontext">WdfObjectAllocateContext</a> to add the context space to a request object before the driver calls <b>WdfRequestForwardToParentDeviceIoQueue</b>. On the other hand, if the driver called <b>WdfDeviceInitSetRequestAttributes</b> for the <i>child</i> device's request objects, and if the parent device's request objects use context space that is equal to or smaller than the child device's context space, the driver can use the request object's context space without calling <b>WdfObjectAllocateContext</b>.

Currently, the driver must use the <a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_forward_options_flags">send and forget option</a> for all requeued I/O requests. Therefore, be aware that by the time that the framework deletes a requeued request object, it might have already removed the child device that originally received the request object. Thus, the driver must not use the <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> function of a requeued request object to access child device resources, because the resources might be removed before the <i>EvtCleanupCallback</i> or <i>EvtDestroyCallback</i> function runs.

For more information about <b>WdfRequestForwardToParentDeviceIoQueue</b>, see <a href="/windows-hardware/drivers/wdf/requeuing-i-o-requests">Requeuing I/O Requests</a>.


#### Examples

The following code example first determines the parent device of a device that received an I/O request, and then it requeues the I/O request to the parent device's default I/O queue.

```cpp
WDFDEVICE device, parentDevice;
WDF_REQUEST_FORWARD_OPTIONS forwardOptions;
NTSTATUS status;

device = WdfIoQueueGetDevice(WdfRequestGetIoQueue(Request));
parentDevice = WdfPdoGetParent(device);

WDF_REQUEST_FORWARD_OPTIONS_INIT(&forwardOptions);
status = WdfRequestForwardToParentDeviceIoQueue(
             Request,
             WdfDeviceGetDefaultQueue(parentDevice),
             &forwardOptions
             );
if (!NT_SUCCESS(status)) {
    WdfRequestComplete(
                       Request,
                       status
                       );
  }
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent">WdfPdoInitAllowForwardingRequestToParent</a>