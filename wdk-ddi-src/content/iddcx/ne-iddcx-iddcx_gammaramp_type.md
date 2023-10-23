---
UID: NE:iddcx.IDDCX_GAMMARAMP_TYPE
title: IDDCX_GAMMARAMP_TYPE (iddcx.h)
description: Learn more about the IDDCX_GAMMARAMP_TYPE enumeration.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDDCX_GAMMARAMP_TYPE enumeration"]
ms.keywords: IDDCX_GAMMARAMP_TYPE, IDDCX_GAMMARAMP_TYPE enumeration [Display Devices], IDDCX_GAMMARAMP_TYPE_DEFAULT, IDDCX_GAMMARAMP_TYPE_RGB256x3x16, IDDCX_GAMMARAMP_TYPE_UNINITIALIZED, display.iddcx_gammaramp_type, iddcx/IDDCX_GAMMARAMP_TYPE, iddcx/IDDCX_GAMMARAMP_TYPE_DEFAULT, iddcx/IDDCX_GAMMARAMP_TYPE_RGB256x3x16, iddcx/IDDCX_GAMMARAMP_TYPE_UNINITIALIZED
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.typenames: 
f1_keywords:
 - IDDCX_GAMMARAMP_TYPE
 - iddcx/IDDCX_GAMMARAMP_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_GAMMARAMP_TYPE
---

# IDDCX_GAMMARAMP_TYPE enumeration

## -description

A **IDDCX_GAMMARAMP_TYPE** value indicates the type of gamma ramp being set.

## -enum-fields

### -field IDDCX_GAMMARAMP_TYPE_UNINITIALIZED:0

Indicates that an **IDDCX_GAMMARAMP_TYPE** variable has not yet been assigned a meaningful value.

### -field IDDCX_GAMMARAMP_TYPE_DEFAULT:1

The gamma ramp is the default ramp.

### -field IDDCX_GAMMARAMP_TYPE_RGB256x3x16:2

The gamma lookup table that [**pGammaRampData**](ns-iddcx-idarg_in_set_gammaramp.md) points to contains an array of [**IDDCX_GAMMARAMP_RGB256x3x16**](ns-iddcx-iddcx_gammaramp_rgb256x3x16.md) structures.

### -field IDDCX_GAMMARAMP_TYPE_3x4_COLORSPACE_TRANSFORM:3

The gamma lookup table that [**pGammaRampData**](ns-iddcx-idarg_in_set_gammaramp.md) points to contains an array of [**IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM**](ns-iddcx-iddcx_gammaramp_3x4_colorspace_transform.md) structures.
Available starting in Windows 11, version 22H2 September Update (IddCx version 1.10).

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP**](nc-iddcx-evt_idd_cx_monitor_set_gamma_ramp.md)

[**IDARG_IN_SET_GAMMARAMP**](ns-iddcx-idarg_in_set_gammaramp.md)
