---
UID: NE:wdfio._WDF_IO_FORWARD_PROGRESS_ACTION
title: _WDF_IO_FORWARD_PROGRESS_ACTION (wdfio.h)
description: The WDF_IO_FORWARD_PROGRESS_ACTION enumeration identifies actions that the framework can take for an I/O request packet (IRP) that your driver examines during a low-memory situation.
old-location: wdf\wdf_io_forward_progress_action.htm
tech.root: wdf
ms.assetid: 4d63c908-8ae3-4df4-826f-9d87ea6c24ad
ms.date: 02/26/2018
keywords: ["WDF_IO_FORWARD_PROGRESS_ACTION enumeration"]
ms.keywords: DFQueueObjectRef_d1ee566a-9887-44de-aef5-a13f64e7603c.xml, WDF_IO_FORWARD_PROGRESS_ACTION, WDF_IO_FORWARD_PROGRESS_ACTION enumeration, WdfIoForwardProgressActionFailRequest, WdfIoForwardProgressActionInvalid, WdfIoForwardProgressActionUseReservedRequest, _WDF_IO_FORWARD_PROGRESS_ACTION, kmdf.wdf_io_forward_progress_action, wdf.wdf_io_forward_progress_action, wdfio/WDF_IO_FORWARD_PROGRESS_ACTION, wdfio/WdfIoForwardProgressActionFailRequest, wdfio/WdfIoForwardProgressActionInvalid, wdfio/WdfIoForwardProgressActionUseReservedRequest
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
targetos: Windows
req.typenames: WDF_IO_FORWARD_PROGRESS_ACTION
f1_keywords:
 - _WDF_IO_FORWARD_PROGRESS_ACTION
 - wdfio/_WDF_IO_FORWARD_PROGRESS_ACTION
 - WDF_IO_FORWARD_PROGRESS_ACTION
 - wdfio/WDF_IO_FORWARD_PROGRESS_ACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfio.h
api_name:
 - WDF_IO_FORWARD_PROGRESS_ACTION
---

# _WDF_IO_FORWARD_PROGRESS_ACTION enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_IO_FORWARD_PROGRESS_ACTION</b> enumeration identifies actions that the framework can take for an I/O request packet (IRP) that your driver examines during a low-memory situation.

## -enum-fields

### -field WdfIoForwardProgressActionInvalid

For internal use only.

### -field WdfIoForwardProgressActionFailRequest

The framework will complete the current I/O request with an error status value.

### -field WdfIoForwardProgressActionUseReservedRequest

The framework will use a reserved request object, if one is available, for the current I/O request.

## -remarks

The <b>WDF_IO_FORWARD_PROGRESS_ACTION</b> enumeration is used as the return value for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress">EvtIoWdmIrpForForwardProgress</a> callback function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress">EvtIoWdmIrpForForwardProgress</a>

