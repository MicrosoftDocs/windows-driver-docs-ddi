---
UID: NE:d3dukmdt._D3DDDI_GAMMARAMP_TYPE
title: D3DDDI_GAMMARAMP_TYPE (d3dukmdt.h)
description: Learn more about the D3DDDI_GAMMARAMP_TYPE enumeration.
tech.root: display
ms.date: 05/21/2024
keywords: ["D3DDDI_GAMMARAMP_TYPE enumeration"]
ms.keywords: D3DDDI_GAMMARAMP_DEFAULT, D3DDDI_GAMMARAMP_DXGI_1, D3DDDI_GAMMARAMP_MATRIX_3x4, D3DDDI_GAMMARAMP_RGB256x3x16, D3DDDI_GAMMARAMP_TYPE, D3DDDI_GAMMARAMP_TYPE enumeration [Display Devices], D3DDDI_GAMMARAMP_UNINITIALIZED, DmEnums_fc19c762-0156-4602-97ea-0b3865012161.xml, _D3DDDI_GAMMARAMP_TYPE, d3dukmdt/D3DDDI_GAMMARAMP_DEFAULT, d3dukmdt/D3DDDI_GAMMARAMP_DXGI_1, d3dukmdt/D3DDDI_GAMMARAMP_MATRIX_3x4, d3dukmdt/D3DDDI_GAMMARAMP_RGB256x3x16, d3dukmdt/D3DDDI_GAMMARAMP_TYPE, d3dukmdt/D3DDDI_GAMMARAMP_UNINITIALIZED, display.d3dddi_gammaramp_type
req.header: d3dukmdt.h
req.construct-type: enumeration
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: D3DDDI_GAMMARAMP_TYPE
f1_keywords:
 - _D3DDDI_GAMMARAMP_TYPE
 - d3dukmdt/_D3DDDI_GAMMARAMP_TYPE
 - D3DDDI_GAMMARAMP_TYPE
 - d3dukmdt/D3DDDI_GAMMARAMP_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_GAMMARAMP_TYPE
 - D3DDDI_GAMMARAMP_TYPE
---

# D3DDDI_GAMMARAMP_TYPE enumeration (d3dukmdt.h)



## -description

The **D3DDDI_GAMMARAMP_TYPE** enumeration indicates the type of gamma ramp used in a video present path.

## -enum-fields

### -field D3DDDI_GAMMARAMP_UNINITIALIZED

Indicates that a variable of type **D3DDDI_GAMMARAMP_TYPE** has not yet been assigned a meaningful value.

### -field D3DDDI_GAMMARAMP_DEFAULT

Indicates the default gamma ramp should be used.

### -field D3DDDI_GAMMARAMP_RGB256x3x16

Indicates that the gamma lookup table contains three arrays, one each for the red, green, and blue color channels. Each array has 256 16-bit values.

### -field D3DDDI_GAMMARAMP_DXGI_1

Indicates that the gamma lookup table is described by a [**D3DDDI_GAMMA_RAMP_DXGI_1**](ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1.md) structure.

### -field D3DDDI_GAMMARAMP_MATRIX_3x4

Indicates that the color space transform is defined by a D3DDDI_3X4_COLORSPACE_TRANSFORM structure.

### -field D3DDDI_GAMMARAMP_MATRIX_V2

Indicates that the color space transform is defined by a D3DKMDT_COLORSPACE_TRANSFORM_MATRIX_V2 structure.

## -remarks

The **GammaRamp** member of the [**D3DKMDT_VIDPN_PRESENT_PATH**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md) structure is a [**D3DKMDT_GAMMA_RAMP**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_gamma_ramp.md) structure. The **Type** member of the D3DKMDT_GAMMA_RAMP structure is a D3DDDI_GAMMARAMP_TYPE value.

## -see-also

[**D3DKMDT_COLOR_BASIS**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_color_basis.md)
