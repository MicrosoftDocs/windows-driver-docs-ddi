---
UID: NC:wdfio.EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES
title: EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES (wdfio.h)
description: A driver's EvtIoAllocateRequestResources callback function allocates request-specific resources that the driver requires to process the specified request.
old-location: wdf\evtioallocaterequestresources.htm
tech.root: wdf
ms.assetid: 6a60c563-582a-4919-bf0f-919deb3055d3
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback function"]
ms.keywords: DFQueueObjectRef_85702d4a-4861-4512-a392-f106e038d3be.xml, EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES, EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback, EvtIoAllocateRequestResources, EvtIoAllocateRequestResources callback function, kmdf.evtioallocaterequestresources, wdf.evtioallocaterequestresources, wdfio/EvtIoAllocateRequestResources
f1_keywords:
 - "wdfio/EvtIoAllocateRequestResources"
 - "EvtIoAllocateRequestResources"
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
req.irql: <=DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfio.h
api_name:
- EvtIoAllocateRequestResources
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_ALLOCATE_REQUEST_RESOURCES callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtIoAllocateRequestResources</i> callback function allocates request-specific resources that the driver requires to process the specified request.


## -parameters




### -param Queue [in]

A handle to an I/O queue object.


### -param Request [in]

A handle to a request object that the framework has created. The framework has not yet added the request object to the I/O queue that the <i>Queue</i> parameter's handle specifies.


## -returns



The <i>EvtIoAllocateRequestResources</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



A driver can register an <i>EvtIoAllocateRequestResources</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoAllocateRequestResources</i> callback function, the framework calls the function immediately after it creates a request object for an I/O request packet (IRP) that the I/O manager has sent to your driver. 

The callback function can allocate resources that your driver will require to process the request later, after the driver has obtained the request object from the I/O queue that the <i>Queue</i> parameter's handle specifies.

If the callback function successfully allocates resources and returns STATUS_SUCCESS, the framework will eventually deliver the request object to the driver.

If a resource allocation error occurs, such as a low memory situation, the callback function must return an error status value. In this case, the framework follows the driver's forward progress policy, which the driver previously specified with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_forward_progress_reserved_policy">WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</a> value when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>.

For more information about the <i>EvtIoAllocateRequestResources</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">Guaranteeing Forward Progress of I/O Operations</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL. If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request">EvtIoAllocateResourcesForReservedRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>
 

 

