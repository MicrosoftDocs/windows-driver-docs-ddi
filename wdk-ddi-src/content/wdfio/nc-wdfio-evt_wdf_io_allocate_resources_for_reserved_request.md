---
UID: NC:wdfio.EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST
title: EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST (wdfio.h)
description: A driver's EvtIoAllocateResourcesForReservedRequest callback function allocates request-specific resources that the driver can use to process an I/O request in the future.
old-location: wdf\evtioallocateresourcesforreservedrequest.htm
tech.root: wdf
ms.assetid: 07ba6437-655b-417a-87a8-5374812ca4d7
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST callback function"]
ms.keywords: DFQueueObjectRef_7fafb899-1038-409b-af8e-f45776b18abe.xml, EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST, EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST callback, EvtIoAllocateResourcesForReservedRequest, EvtIoAllocateResourcesForReservedRequest callback function, kmdf.evtioallocateresourcesforreservedrequest, wdf.evtioallocateresourcesforreservedrequest, wdfio/EvtIoAllocateResourcesForReservedRequest
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST
 - wdfio/EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfio.h
api_name:
 - EvtIoAllocateResourcesForReservedRequest
---

# EVT_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtIoAllocateResourcesForReservedRequest</i> callback function allocates request-specific resources that the driver can use to process an I/O request in the future. The framework is pre-allocating the specified request object for future use in low-memory situations.

## -parameters

### -param Queue 

[in]
A handle to an I/O queue object.

### -param Request 

[in]
A handle to a request object that the framework has created for use during future low-memory situations.

## -returns

The <i>EvtIoAllocateResourcesForReservedRequest</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

## -remarks

A driver can register an <i>EvtIoAllocateResourcesForReservedRequest</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoAllocateResourcesForReservedRequest</i> callback function, the framework calls the function immediately after it creates a request object that it reserves for low-memory situations. 

The callback function can allocate resources that your driver will require to process a request later, if the framework uses the reserved request because of a low-memory situation.

To allocate memory for request-specific resources, an <i>EvtIoAllocateResourcesForReservedRequest</i> callback function might call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectallocatecontext">WdfObjectAllocateContext</a>, specifying the request object handle that the <i>Request</i> parameter specifies. 

Alternatively or additionally, your driver might call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. As a result, the framework will allocate context space for each reserved request object when it creates the object. 

If your driver allocates object context space for reserved request objects, the driver must reinitialize the context space when it completes an I/O request that uses a reserved request object. The framework does not reinitialize the context space of reserved request objects after use.

If your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a> and specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function for its request objects, the framework calls these callback functions for its reserved request objects only when it deletes the associated I/O queues.

The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handlers</a> can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestisreserved">WdfRequestIsReserved</a> to determine if reserved request objects are being used.

For more information about how to use object context space, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

If the callback function successfully allocates resources, it should return STATUS_SUCCESS.

If a resource allocation error occurs, such as a low memory situation, the callback function must return an error status value. In this case, the framework stops allocating reserved request objects and uses the callback function's return value as the return value for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>.

For more information about the <i>EvtIoAllocateResourcesForReservedRequest</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_allocate_request_resources">EvtIoAllocateRequestResources</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestisreserved">WdfRequestIsReserved</a>

