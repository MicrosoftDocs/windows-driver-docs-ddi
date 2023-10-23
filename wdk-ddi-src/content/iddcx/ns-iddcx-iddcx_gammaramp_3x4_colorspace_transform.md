---
UID: NS:iddcx.IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM
tech.root: display
title: IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM
f1_keywords:
 - IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM
 - iddcx/IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM
---

## -description

The **IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM** structure contains a 3x4 color space gamma ramp for a monitor.

## -struct-fields

### -field MatrixEnabled

A Boolean value. If set TRUE, **ColorMatrix3x4** contains a valid matrix and **ScalarMultiplier** contains a valid value, both of which should be applied.

### -field ColorMatrix3x4[3]

A 3x3 matrix and 3x1 addition to be applied to each pixel, stored in row-major order. Transforms colors within CIEXYZ.

### -field ScalarMultiplier

A scalar to be multiplied into each element of **ColorMatrix3x4**.

### -field LutEnabled

A Boolean value. If set TRUE, **LookupTable1D** contains a valid table that should be applied.

### -field LookupTable1D[4096]

A one-dimensional look-up table of [**IDDCX_RGB**](ns-iddcx-iddcx_rgb.md) structures that transform colors within the color space specified by [**IDDCX_PATH2::WireFormatInfo.ColorSpace**](ns-iddcx-iddcx_path2.md).

## -remarks

The gamma lookup table can contain a 3x4 matrix, a scalar multiplier and a LUT. This value is only specified for console drivers.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP**](nc-iddcx-evt_idd_cx_monitor_set_gamma_ramp.md)

[**IDARG_IN_SET_GAMMARAMP**](ns-iddcx-idarg_in_set_gammaramp.md)

[**IDDCX_RGB**](ns-iddcx-iddcx_rgb.md)
