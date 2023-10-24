---
UID: NS:iddcx.IDDCX_GAMMARAMP_RGB256x3x16
tech.root: display
title: IDDCX_GAMMARAMP_RGB256x3x16
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_GAMMARAMP_RGB256x3x16 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10
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
 - IDDCX_GAMMARAMP_RGB256x3x16
f1_keywords:
 - IDDCX_GAMMARAMP_RGB256x3x16
 - iddcx/IDDCX_GAMMARAMP_RGB256x3x16
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_GAMMARAMP_RGB256x3x16
---

## -description

The **IDDCX_GAMMARAMP_RGB256x3x16** structure contains an RGB gamma ramp for a monitor.

## -struct-fields

### -field Red[256]

An array of 16-bit values that specify the gamma function for the red color channel.

### -field Green[256]

An array of 16-bit values that specify the gamma function for the green color channel.

### -field Blue[256]

An array of 16-bit values that specify the gamma function for the blue color channel.

## -remarks

**IDDCX_GAMMARAMP_RGB256x3x16** has three arrays, one each for the red, green, and blue color channels. Each array has 256 16-bit values.

## -see-also

[**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP**](nc-iddcx-evt_idd_cx_monitor_set_gamma_ramp.md)

[**IDARG_IN_SET_GAMMARAMP**](ns-iddcx-idarg_in_set_gammaramp.md)
