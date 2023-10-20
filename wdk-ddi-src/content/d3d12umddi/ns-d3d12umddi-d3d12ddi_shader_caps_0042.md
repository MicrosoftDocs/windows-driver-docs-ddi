---
UID: NS:d3d12umddi.D3D12DDI_SHADER_CAPS_0042
title: D3D12DDI_SHADER_CAPS_0042 (d3d12umddi.h)
description: Learn more about the D3D12DDI_SHADER_CAPS_0042 structure.
ms.date: 10/19/2023
keywords: ["D3D12DDI_SHADER_CAPS_0042 structure"]
ms.keywords: D3D12DDI_SHADER_CAPS_0042, D3D12DDI_SHADER_CAPS_0042,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_SHADER_CAPS_0042
targetos: Windows
tech.root: display
f1_keywords:
 - D3D12DDI_SHADER_CAPS_0042
 - d3d12umddi/D3D12DDI_SHADER_CAPS_0042
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_SHADER_CAPS_0042
product:
 - Windows
---

# D3D12DDI_SHADER_CAPS_0042 structure

## -description

The **D3D12DDI_SHADER_CAPS_0042** structure contains display device shader capabilities that the driver supports.

## -struct-fields

### -field MinPrecision

A bitwise OR of [**D3D12DDI_SHADER_MIN_PRECISION**](ne-d3d12umddi-d3d12ddi_shader_min_precision.md) values that describe the driver's minimum precision support options for shaders.

### -field DoubleOps

A Boolean value that specifies whether the driver allows **double** types for shader operations (TRUE indicates driver support).

### -field ShaderSpecifiedStencilRef

A Boolean value that specifies whether the driver supports pixel shader stencil ref (TRUE indicates driver support).

### -field TypedUAVLoadAdditionalFormats

A Boolean value that specifies whether the driver supports the loading of additional formats for typed unordered-access views (UAVs) (TRUE indicates driver support).

### -field ROVs

A Boolean value that specifies whether the driver supports [rasterizer ordered views](/windows/win32/direct3d12/directx-12-glossary) (TRUE indicates driver support).

### -field WaveOps

A Boolean value that specifies whether the driver supports wave operations.

### -field WaveLaneCountMin

Specifies the minimum number of lanes in the SIMD (single instruction, multiple data) wave that the driver supports.

### -field WaveLaneCountMax

Specifies the maximum number of lanes in the SIMD wave that the driver supports.

### -field TotalLaneCount

Specifies the total number of SIMD lanes on the hardware.

### -field Int64Ops

A Boolean value that indicates whether the driver supports 64-bit operations (TRUE indicates driver support).

### -field Native16BitOps

A Boolean value that indicates whether the driver supports native 64-bit operations (TRUE indicates driver support).

## -remarks

The user-mode display driver returns these caps when the D3D runtime calls UMD's [**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md) function with the **Type** member of the [**D3DDDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md) structure set to **D3D12DDICAPS_TYPE_SHADER**.
  
## -see-also

[**D3D12DDI_SHADER_CAPS_0084**](ns-d3d12umddi-d3d12ddi_shader_caps_0084.md)

[**D3D12DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**D3DDDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
