---
UID: NS:wdfrequest._WDF_REQUEST_FORWARD_OPTIONS
title: _WDF_REQUEST_FORWARD_OPTIONS (wdfrequest.h)
description: The WDF_REQUEST_FORWARD_OPTIONS structure contains options for requeuing an I/O request from a child device's I/O queue to the parent device's I/O queue.
old-location: wdf\wdf_request_forward_options.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_FORWARD_OPTIONS structure"]
ms.keywords: "*PWDF_REQUEST_FORWARD_OPTIONS, DFRequestObjectRef_878a982e-6fe9-4bfc-ad5c-165ef7590b79.xml, PWDF_REQUEST_FORWARD_OPTIONS, PWDF_REQUEST_FORWARD_OPTIONS structure pointer, WDF_REQUEST_FORWARD_OPTIONS, WDF_REQUEST_FORWARD_OPTIONS structure, _WDF_REQUEST_FORWARD_OPTIONS, kmdf.wdf_request_forward_options, wdf.wdf_request_forward_options, wdfrequest/PWDF_REQUEST_FORWARD_OPTIONS, wdfrequest/WDF_REQUEST_FORWARD_OPTIONS"
req.header: wdfrequest.h
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
req.typenames: WDF_REQUEST_FORWARD_OPTIONS, *PWDF_REQUEST_FORWARD_OPTIONS
f1_keywords:
 - _WDF_REQUEST_FORWARD_OPTIONS
 - wdfrequest/_WDF_REQUEST_FORWARD_OPTIONS
 - PWDF_REQUEST_FORWARD_OPTIONS
 - wdfrequest/PWDF_REQUEST_FORWARD_OPTIONS
 - WDF_REQUEST_FORWARD_OPTIONS
 - wdfrequest/WDF_REQUEST_FORWARD_OPTIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfrequest.h
api_name:
 - _WDF_REQUEST_FORWARD_OPTIONS
 - PWDF_REQUEST_FORWARD_OPTIONS
 - WDF_REQUEST_FORWARD_OPTIONS
---

# _WDF_REQUEST_FORWARD_OPTIONS structure


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure contains options for requeuing an I/O request from a child device's I/O queue to the parent device's I/O queue.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Flags

A bitwise OR of <a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_forward_options_flags">WDF_REQUEST_FORWARD_OPTIONS_FLAGS</a>-typed flags.

## -remarks

The <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure is used as input to the <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a> method.

Your driver must call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_forward_options_init">WDF_REQUEST_FORWARD_OPTIONS_INIT</a> to initialize the <b>WDF_REQUEST_FORWARD_OPTIONS</b> structure before the driver calls <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_forward_options_flags">WDF_REQUEST_FORWARD_OPTIONS_FLAGS</a>

