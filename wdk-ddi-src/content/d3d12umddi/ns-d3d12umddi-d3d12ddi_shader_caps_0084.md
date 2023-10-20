---
UID: NS:d3d12umddi.D3D12DDI_SHADER_CAPS_0084
tech.root:display
title: D3D12DDI_SHADER_CAPS_0084
ms.date: 10/19/2023
targetos: Windows
description: Learn more about the D3D12DDI_SHADER_CAPS_0084 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_SHADER_CAPS_0084
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_SHADER_CAPS_0084
f1_keywords:
 - D3D12DDI_SHADER_CAPS_0084
 - d3d12umddi/D3D12DDI_SHADER_CAPS_0084
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_SHADER_CAPS_0084
---

## -description

The **D3D12DDI_SHADER_CAPS_0084** structure contains display device shader capabilities that the driver supports.

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

### -field AtomicInt64OnTypedResource

A Boolean value that indicates whether the driver supports 64-bit typed atomic operations on a resource (TRUE indicates driver support).

### -field AtomicInt64OnGroupShared

A Boolean value that indicates whether the driver supports 64-bit typed atomic operations on group shared memory (TRUE indicates driver support).

### -field DerivativesInMeshAndAmplificationShaders

A Boolean value that indicates whether the driver supports quad-based derivative operations to mesh and amplification shaders (TRUE indicates driver support).

### -field WaveMMATier

A [**D3D12DDI_WAVE_MMA_TIER**](ns-d3d12umddi-d3d12ddi_wave_mma_tier.md) value that indicates the wave matrix-matrix multiply-accumulate (MMA) tier supported by the driver.

### -field AtomicInt64OnDescriptorHeapResource

A Boolean value that indicates whether the driver supports 64-bit typed atomic operations on resources in descriptor heaps (TRUE indicates driver support).

## -remarks

The user-mode display driver returns these caps when the D3D runtime calls UMD's [**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md) function with the **Type** member of the [**D3DDDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md) structure set to **D3D12DDICAPS_TYPE_SHADER**.
  
## -see-also

[**D3D12DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**D3DDDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
