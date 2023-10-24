---
UID: NS:iddcx.IDDCX_RGB
tech.root: display
title: IDDCX_RGB
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_RGB structure.
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
 - IDDCX_RGB
f1_keywords:
 - IDDCX_RGB
 - iddcx/IDDCX_RGB
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_RGB
---

## -description

The **IDDCX_RGB** structure contains a red, green, and blue value for gamma ramp data.

## -struct-fields

### -field Red

A floating point value that is used to describe the gamma function for the red color channel.

### -field Green

A floating point value that is used to describe the gamma function for the green color channel.

### -field Blue

A floating point value that is used to describe the gamma function for the blue color channel.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP**](nc-iddcx-evt_idd_cx_monitor_set_gamma_ramp.md)

[**IDARG_IN_SET_GAMMARAMP**](ns-iddcx-idarg_in_set_gammaramp.md)

[**IDDCX_GAMMARAMP_3X4_COLORSPACE_TRANSFORM**](ns-iddcx-iddcx_gammaramp_3x4_colorspace_transform.md)
