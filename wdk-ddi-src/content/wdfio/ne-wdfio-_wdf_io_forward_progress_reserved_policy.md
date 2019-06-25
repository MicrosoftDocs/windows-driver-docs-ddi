---
UID: NE:wdfio._WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY
title: _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY (wdfio.h)
description: The WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY enumeration identifies actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.
old-location: wdf\wdf_io_forward_progress_reserved_policy.htm
tech.root: wdf
ms.assetid: 6d530cf2-de06-4aa3-9f4d-08619906c9ed
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_e035ecd7-f728-4d88-80a8-763ab3eb90ab.xml, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY enumeration, WdfIoForwardProgressInvalidPolicy, WdfIoForwardProgressReservedPolicyAlwaysUseReservedRequest, WdfIoForwardProgressReservedPolicyPagingIO, WdfIoForwardProgressReservedPolicyUseExamine, _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY, kmdf.wdf_io_forward_progress_reserved_policy, wdf.wdf_io_forward_progress_reserved_policy, wdfio/WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY, wdfio/WdfIoForwardProgressInvalidPolicy, wdfio/WdfIoForwardProgressReservedPolicyAlwaysUseReservedRequest, wdfio/WdfIoForwardProgressReservedPolicyPagingIO, wdfio/WdfIoForwardProgressReservedPolicyUseExamine
ms.topic: enum
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfio.h
api_name:
- WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY
---

# _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</b> enumeration identifies actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.


## -enum-fields




### -field WdfIoForwardProgressInvalidPolicy


### -field WdfIoForwardProgressReservedPolicyAlwaysUseReservedRequest

In a low-memory situation, the framework always uses a reserved request object, if one is available.


### -field WdfIoForwardProgressReservedPolicyUseExamine

In a low-memory situation, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress">EvtIoWdmIrpForForwardProgress</a> callback function.


### -field WdfIoForwardProgressReservedPolicyPagingIO

In a low-memory situation, if the <b>Flags</b> member of the I/O request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a> structure indicates a paging operation, the framework uses a reserved request object, if one is available. If the I/O request is not a paging operation, the framework completes the I/O request with an error status value.


## -remarks



The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</b> enumeration is used as a member type in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/ns-wdfio-_wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.



