---
UID: NS:avc._AVC_PIN_COUNT
title: _AVC_PIN_COUNT (avc.h)
description: The AVC_PIN_COUNT structure specifies the number of pins on an AV/C subunit device.
old-location: stream\avc_pin_count.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["AVC_PIN_COUNT structure"]
ms.keywords: "*PAVC_PIN_COUNT, AVC_PIN_COUNT, AVC_PIN_COUNT structure [Streaming Media Devices], PAVC_PIN_COUNT, PAVC_PIN_COUNT structure pointer [Streaming Media Devices], _AVC_PIN_COUNT, avc/AVC_PIN_COUNT, avc/PAVC_PIN_COUNT, avcref_693c28a9-c746-4116-aee7-0de54ce08565.xml, stream.avc_pin_count"
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
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
req.typenames: AVC_PIN_COUNT, *PAVC_PIN_COUNT
f1_keywords:
 - _AVC_PIN_COUNT
 - avc/_AVC_PIN_COUNT
 - PAVC_PIN_COUNT
 - avc/PAVC_PIN_COUNT
 - AVC_PIN_COUNT
 - avc/AVC_PIN_COUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - _AVC_PIN_COUNT
 - PAVC_PIN_COUNT
 - AVC_PIN_COUNT
---

# _AVC_PIN_COUNT structure


## -description

The AVC_PIN_COUNT structure specifies the number of pins on an AV/C subunit device.

## -struct-fields

### -field PinCount

This value is filled in by <i>avc.sys</i> on return from the <b>AVC_FUNCTION_GET_PIN_COUNT</b> function.

## -remarks

This structure is used with the <a href="/windows-hardware/drivers/stream/avc-function-get-pin-count">AVC_FUNCTION_GET_PIN_COUNT</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> For information about building and sending an AV/C command.

## -see-also

<a href="/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="/windows-hardware/drivers/stream/avc-function-get-pin-count">AVC_FUNCTION_GET_PIN_COUNT</a>



<a href="/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>

