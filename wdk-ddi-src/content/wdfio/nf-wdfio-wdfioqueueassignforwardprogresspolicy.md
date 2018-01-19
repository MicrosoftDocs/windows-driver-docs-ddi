---
UID: NF:wdfio.WdfIoQueueAssignForwardProgressPolicy
title: WdfIoQueueAssignForwardProgressPolicy function
author: windows-driver-content
description: The WdfIoQueueAssignForwardProgressPolicy method enables the framework's ability to guarantee forward progress for a specified I/O queue.
old-location: wdf\wdfioqueueassignforwardprogresspolicy.htm
old-project: wdf
ms.assetid: 9512ecf2-ca59-4df8-bb60-c644444bc6fa
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoQueueAssignForwardProgressPolicy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.alt-api: WdfIoQueueAssignForwardProgressPolicy
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueAssignForwardProgressPolicy function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoQueueAssignForwardProgressPolicy</b> method enables the framework's ability to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guarantee forward progress</a> for a specified I/O queue. 



## -syntax

````
NTSTATUS WdfIoQueueAssignForwardProgressPolicy(
  _In_ WDFQUEUE                              Queue,
  _In_ PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY ForwardProgressPolicy
);
````


## -parameters

### -param Queue [in]

A handle to a framework queue object.


### -param ForwardProgressPolicy [in]

A pointer to a driver-allocated <a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.


## -returns
<b>WdfIoQueueAssignForwardProgressPolicy</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of these values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid. 
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure is incorrect.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The amount of available memory is too low.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>. In addition, if your driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md">EvtIoAllocateResourcesForReservedRequest</a> callback function returns an error status value, <b>WdfIoQueueAssignForwardProgressPolicy</b> returns that value.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The<b>WdfIoQueueAssignForwardProgressPolicy</b> method creates request objects that the framework reserves for low-memory situations and registers callback functions that the framework calls to handle low-memory situations.

In KMDF version 1.9, the I/O queue that the <i>Queue</i> parameter represents must be a device's default I/O queue, or a queue for which your driver has called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md">WdfDeviceConfigureRequestDispatching</a>. The driver can call <b>WdfIoQueueAssignForwardProgressPolicy</b> any time after it has called <b>WdfDeviceConfigureRequestDispatching</b>.

In KMDF versions 1.11 and later,  the I/O queue that the <i>Queue</i> parameter represents can be any queue that receives a request directly from the framework. For example, the driver might specify a queue to which it will <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">dynamically forward IRPs</a>.

Before <b>WdfIoQueueAssignForwardProgressPolicy</b> returns, the framework does the following:

Creates and stores the number of request objects that the driver has specified for the <b>TotalForwardProgressRequests</b> member of the <a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.

If the driver previously called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a>, each allocation includes context space that <b>WdfDeviceInitSetRequestAttributes</b> specified. 

Calls the driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md">EvtIoAllocateResourcesForReservedRequest</a> callback function for each request object that the framework creates.

After the driver has called <b>WdfIoQueueAssignForwardProgressPolicy</b> to create reserved request objects, the framework uses those reserved objects whenever its attempt to create a new request object fails. (Typically, such failures are caused by low memory situations.) 

The framework deletes its reserved request objects only when it deletes the framework queue object that they belong to. If your driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a> and specifies an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback function for its request objects, the framework calls these callback functions for its reserved request objects when it deletes the objects.

For more information about the <b>WdfIoQueueAssignForwardProgressPolicy</b> method and how to use the framework's guaranteed forward progress capability, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.

This code example configures a previously created I/O queue to receive write requests, and then it enables guaranteed forward progress for the queue.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md">EvtIoAllocateResourcesForReservedRequest</a>
</dt>
<dt>
<a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md">WdfDeviceConfigureRequestDispatching</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueAssignForwardProgressPolicy method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

