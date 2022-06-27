---
UID: NS:d3dkmddi._DXGK_COLORTRANSFORMCAPS
title: DXGK_COLORTRANSFORMCAPS (d3dkmddi.h)
description: This structure replaces the DXGK_GAMMARAMPCAPS structure in the DXGK_DRIVERCAPS structure to describe both the gamma and color transform capabilities of the display pipelines.
old-location: display\dxgk_colortransformcaps_.htm
ms.date: 05/24/2022
keywords: ["DXGK_COLORTRANSFORMCAPS structure"]
ms.keywords: DXGK_COLORTRANSFORMCAPS, DXGK_COLORTRANSFORMCAPS , DXGK_COLORTRANSFORMCAPS structure [Display Devices], PDXGK_COLORTRANSFORMCAPS, PDXGK_COLORTRANSFORMCAPS structure pointer [Display Devices], _DXGK_COLORTRANSFORMCAPS, d3dkmddi/DXGK_COLORTRANSFORMCAPS, d3dkmddi/PDXGK_COLORTRANSFORMCAPS, display.dxgk_colortransformcaps_
req.header: d3dkmddi.h
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
tech.root: display
req.typenames: DXGK_COLORTRANSFORMCAPS
f1_keywords:
 - _DXGK_COLORTRANSFORMCAPS
 - d3dkmddi/_DXGK_COLORTRANSFORMCAPS
 - DXGK_COLORTRANSFORMCAPS
 - d3dkmddi/DXGK_COLORTRANSFORMCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_COLORTRANSFORMCAPS
 - DXGK_COLORTRANSFORMCAPS
---

# DXGK_COLORTRANSFORMCAPS structure

## -description

This structure replaces the DXGK_GAMMARAMPCAPS structure in the DXGK_DRIVERCAPS structure to describe both the gamma and color transform capabilities of the display pipelines.

## -struct-fields

### -field Gamma_Rgb256x3x16

Indicates support for a GDI compatible gamma ramp.

### -field Gamma_Dxgi1

Indicates support for a DXGI1 gamma ramp.  These gamma ramps have been defined since WDDM 1.0 but were always required to be supported by any WDDM driver.
Full WDDM drivers are still required to support DXGI1 gamma so should set this flag but drivers for display-only and indirect display will be able to indicate support through this flag.

### -field Transform_3x4Matrix

Indicates support for a 3 by 4 matrix color transform in the display pipeline hardware.

### -field Transform_3x4Matrix_WideColor

Indicates support for a 3 by 4 matrix color transform in the display pipeline hardware when scanning out WideColor data.  Drivers which support this capability must also support Transform_3x4Matrix. The OS will NOT engage WideColorGamut mode unless both this bit and the WideColorSpace cap bits are set.

### -field Transform_3x4Matrix_HighColor

Indicates support for a 3 by 4 matrix color transform in the display pipeline hardware when scanning out HighColor data.  Drivers which support this capability must also support Transform_3x4Matrix_WideColor.

### -field Transform_Matrix_V2

Indicates support for a colorspace transform matrix.

### -field Reserved

This value is reserved for system use.

### -field Value

The combined UINT value.
