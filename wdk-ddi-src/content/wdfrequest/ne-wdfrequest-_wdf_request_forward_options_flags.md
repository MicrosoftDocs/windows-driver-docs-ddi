---
UID: NE:wdfrequest._WDF_REQUEST_FORWARD_OPTIONS_FLAGS
title: _WDF_REQUEST_FORWARD_OPTIONS_FLAGS (wdfrequest.h)
description: The WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_FORWARD_OPTIONS structure.
old-location: wdf\wdf_request_forward_options_flags.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration"]
ms.keywords: DFRequestObjectRef_cad8f6c6-9c76-4dc3-ac3f-3938e5174563.xml, WDF_REQUEST_FORWARD_OPTIONS_FLAGS, WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration, WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET, _WDF_REQUEST_FORWARD_OPTIONS_FLAGS, kmdf.wdf_request_forward_options_flags, wdf.wdf_request_forward_options_flags, wdfrequest/WDF_REQUEST_FORWARD_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET
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
req.typenames: WDF_REQUEST_FORWARD_OPTIONS_FLAGS
f1_keywords:
 - _WDF_REQUEST_FORWARD_OPTIONS_FLAGS
 - wdfrequest/_WDF_REQUEST_FORWARD_OPTIONS_FLAGS
 - WDF_REQUEST_FORWARD_OPTIONS_FLAGS
 - wdfrequest/WDF_REQUEST_FORWARD_OPTIONS_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfrequest.h
api_name:
 - _WDF_REQUEST_FORWARD_OPTIONS_FLAGS
 - WDF_REQUEST_FORWARD_OPTIONS_FLAGS
---

# _WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_REQUEST_FORWARD_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_forward_options">WDF_REQUEST_FORWARD_OPTIONS</a> structure.

## -enum-fields

### -field WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET:0x00000001

If set, the driver does not need to be notified when the request is completed or canceled. The driver does not set a <a href="/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function or call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> for the request.

## -remarks

Currently, drivers must set the WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET flag.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_forward_options">WDF_REQUEST_FORWARD_OPTIONS</a>

