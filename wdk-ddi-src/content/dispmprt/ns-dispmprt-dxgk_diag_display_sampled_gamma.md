---
UID: NS:dispmprt._DXGK_DIAG_DISPLAY_SAMPLED_GAMMA
title: DXGK_DIAG_DISPLAY_SAMPLED_GAMMA
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_DIAG_DISPLAY_SAMPLED_GAMMA structure provides gamma samples during diagnostic data collection.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_DIAG_DISPLAY_SAMPLED_GAMMA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAG_DISPLAY_SAMPLED_GAMMA
 - DXGK_DIAG_DISPLAY_SAMPLED_GAMMA
f1_keywords:
 - dispmprt/_DXGK_DIAG_DISPLAY_SAMPLED_GAMMA
 - dispmprt/DXGK_DIAG_DISPLAY_SAMPLED_GAMMA
dev_langs:
 - c++
---

# DXGK_DIAG_DISPLAY_SAMPLED_GAMMA structure

## -description

The **DXGK_DIAG_DISPLAY_SAMPLED_GAMMA** structure provides gamma samples during diagnostic data collection.

## -struct-fields

### -field Red

[out] MAX_NUM_OF_GAMMA_SAMPLES_FOR_DIAGNOSTICS gamma samples from the red channel, where the samples are equally spaced as much as is possible.

### -field Green

[out] MAX_NUM_OF_GAMMA_SAMPLES_FOR_DIAGNOSTICS gamma samples from the green channel, where the samples are equally spaced as much as is possible.

### -field Blue

[out] MAX_NUM_OF_GAMMA_SAMPLES_FOR_DIAGNOSTICS gamma samples from the blue channel, where the samples are equally spaced as much as is possible.

### -field ColorMatrix

[out] A 3X3 matrix should contain any global scalar multiplier baked in if applicable. If the driver has 3X4 matrix then it is ok to just ignore the last column.

## -remarks

The **DXGK_DIAG_DISPLAY_SAMPLED_GAMMA** structure is a member of the [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure, which is passed in calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) during  diagnostic data collection.

In Windows 10 version 2004 and later, the gamma and CSC matrix requested by the operating system is global and not per plane. For the sampled gamma values, drivers should return the gamma/LUT values from the re-gamma stage so that the OS can get as close to the final gamma curve being applied on the pixels going out of the wire. If internally the drivers have any per plane gamma/LUT then they should just return the values for plane 0. Drivers should not do any complex calculations for the sampled gamma values for the diagnostic interface.

## -see-also

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DXGKARG_GETDISPLAYSTATEINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystateintrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)
