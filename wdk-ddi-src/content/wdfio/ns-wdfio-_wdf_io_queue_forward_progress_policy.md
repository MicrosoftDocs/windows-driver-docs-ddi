---
UID: NS:wdfio._WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY
title: "_WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY"
author: windows-driver-content
description: The WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure contains driver-supplied information that the framework uses to enable guaranteed forward progress for an I/O queue.
old-location: wdf\wdf_io_queue_forward_progress_policy.htm
old-project: wdf
ms.assetid: cee3de1f-eaee-40e9-97a9-979e75e22c0a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfio/WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, DFQueueObjectRef_cfd7143c-1ca1-4ecf-a840-0007971f9197.xml, wdfio/PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure, kmdf.wdf_io_queue_forward_progress_policy, PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure pointer, wdf.wdf_io_queue_forward_progress_policy, *PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, _WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: Any IRQL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfio.h
apiname:
-	WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, *PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</b> structure contains driver-supplied information that the framework uses to enable <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/guaranteeing-forward-progress-of-i-o-operations">guaranteed forward progress</a> for an I/O queue.


## -syntax


````
typedef struct _WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY {
  ULONG                                              Size;
  ULONG                                              TotalForwardProgressRequests;
  WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY            ForwardProgressReservedPolicy;
  WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS   ForwardProgressReservePolicySettings;
  PFN_WDF_IO_ALLOCATE_RESOURCES_FOR_RESERVED_REQUEST EvtIoAllocateResourcesForReservedRequest;
  PFN_WDF_IO_ALLOCATE_REQUEST_RESOURCES              EvtIoAllocateRequestResources;
} WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY, *PWDF_IO_QUEUE_FORWARD_PROGRESS_POLICY;
````


## -struct-fields




### -field Size

The length, in bytes, of this structure.


### -field TotalForwardProgressRequests

The number of request objects that the framework will attempt to reserve for use in low-memory situations. This number must be greater than zero.


### -field ForwardProgressReservedPolicy

A <a href="..\wdfio\ne-wdfio-_wdf_io_forward_progress_reserved_policy.md">WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</a>-typed value that specifies how the framework will allocate request objects during low-memory situations. 


### -field ForwardProgressReservePolicySettings

A <a href="..\wdfio\ns-wdfio-_wdf_io_forward_progress_reserved_policy_settings.md">WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS</a> structure that contains additional values that are specific to the policy that the <b>ForwardProgressReservedPolicy</b> member specifies. This member should be <b>NULL</b> unless the driver provides an <a href="..\wdfio\nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress.md">EvtIoWdmIrpForForwardProgress</a> callback function.


### -field EvtIoAllocateResourcesForReservedRequest

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md">EvtIoAllocateResourcesForReservedRequest</a> callback function, or <b>NULL</b>.


### -field EvtIoAllocateRequestResources

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_request_resources.md">EvtIoAllocateRequestResources</a> callback function, or <b>NULL</b>.


## -remarks



The <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</b> structure is used as input to the <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a> method.

Drivers must initialize the <b>WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</b> structure by calling <a href="..\wdfio\nf-wdfio-wdf_io_queue_forward_progress_policy_default_init.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_DEFAULT_INIT</a>, <a href="..\wdfio\nf-wdfio-wdf_io_queue_forward_progress_policy_examine_init.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_EXAMINE_INIT</a>, or <a href="..\wdfio\nf-wdfio-wdf_io_queue_forward_progress_policy_pagingio_init.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY_PAGINGIO_INIT</a> before they call <a href="..\wdfio\nf-wdfio-wdfioqueueassignforwardprogresspolicy.md">WdfIoQueueAssignForwardProgressPolicy</a>. 



