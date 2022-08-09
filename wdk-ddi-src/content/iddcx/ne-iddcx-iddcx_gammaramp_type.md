---
UID: NE:iddcx.IDDCX_GAMMARAMP_TYPE
title: IDDCX_GAMMARAMP_TYPE (iddcx.h)
description: An enumeration indicating the type of gamma ramp being set.
old-location: display\iddcx_gammaramp_type.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_GAMMARAMP_TYPE enumeration"]
ms.keywords: IDDCX_GAMMARAMP_TYPE, IDDCX_GAMMARAMP_TYPE enumeration [Display Devices], IDDCX_GAMMARAMP_TYPE_DEFAULT, IDDCX_GAMMARAMP_TYPE_RGB256x3x16, IDDCX_GAMMARAMP_TYPE_UNINITIALIZED, display.iddcx_gammaramp_type, iddcx/IDDCX_GAMMARAMP_TYPE, iddcx/IDDCX_GAMMARAMP_TYPE_DEFAULT, iddcx/IDDCX_GAMMARAMP_TYPE_RGB256x3x16, iddcx/IDDCX_GAMMARAMP_TYPE_UNINITIALIZED
req.header: iddcx.h
req.include-header: 
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

The gamma lookup table contains three arrays, one each for the red, green, and blue color channels. Each array has 256 16-bit values.

## -see-also

[**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP**](nc-iddcx-evt_idd_cx_monitor_set_gamma_ramp.md)

[**IDARG_IN_SET_GAMMARAMP**](ns-iddcx-idarg_in_set_gammaramp.md)
