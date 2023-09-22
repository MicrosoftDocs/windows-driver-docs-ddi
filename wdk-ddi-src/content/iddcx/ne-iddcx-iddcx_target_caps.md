---
UID: NE:iddcx.IDDCX_TARGET_CAPS
tech.root: display
title: IDDCX_TARGET_CAPS
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_TARGET_CAPS enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_TARGET_CAPS
f1_keywords:
 - IDDCX_TARGET_CAPS
 - iddcx/IDDCX_TARGET_CAPS
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_TARGET_CAPS
---

## -description

An **IDDCX_TARGET_CAPS** enumeration value identifies the capabilities of a target.

## -enum-fields

### -field IDDCX_TARGET_CAPS_NONE:0

The target doesn't support any of the available capabilities.

### -field IDDCX_TARGET_CAPS_WIDE_COLOR_SPACE:0x1

If set, the driver has the ability to transform RGB values from the gamut defined by the sRGB/709 primaries to the monitor's primaries. The driver can also send any necessary control signaling to the monitor to indicate the correct interpretation of the pixel data being sent. This includes handling signed input in the range (-2.0 to 2.0). The driver must do this with all supported input surface formats, including 8888 and FP16.

### -field IDDCX_TARGET_CAPS_HIGH_COLOR_SPACE:0x2

If set, the driver supports all of the above WideColorSpace gamut functionality and also has the ability to apply the appropriate transfer curve for that display. This means accepting canonical color space data in the range [-128.0 to 256.0] and sending any necessary control signaling to the connected display to indicate the correct interpretation.

Setting **IDDCX_TARGET_CAPS_HIGH_COLOR_SPACE** is not a replacement for setting **IDDCX_TARGET_CAPS_WIDE_COLOR_SPACE**. Drivers that support **IDDCX_TARGET_CAPS_HIGH_COLOR_SPACE** should also set **IDDCX_TARGET_CAPS_WIDE_COLOR_SPACE**.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO**](nc-iddcx-evt_idd_cx_adapter_query_target_info.md)

[**IDARG_OUT_QUERYTARGET_INFO**](ns-iddcx-idarg_out_querytarget_info.md)
