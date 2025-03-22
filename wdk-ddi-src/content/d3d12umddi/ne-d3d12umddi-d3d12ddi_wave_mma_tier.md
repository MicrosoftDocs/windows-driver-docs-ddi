---
UID: NE:d3d12umddi.D3D12DDI_WAVE_MMA_TIER
tech.root: display
title: D3D12DDI_WAVE_MMA_TIER
ms.date: 05/06/2024
targetos: Windows
description: Learn more about the D3D12DDI_WAVE_MMA_TIER enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_WAVE_MMA_TIER
f1_keywords:
 - D3D12DDI_WAVE_MMA_TIER
 - d3d12umddi/D3D12DDI_WAVE_MMA_TIER
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WAVE_MMA_TIER
---

# D3D12DDI_WAVE_MMA_TIER enumeration (d3d12umddi.h)

## -description

A **D3D12DDI_WAVE_MMA_TIER** enumeration value indicates the driver's support for wave matrix-matrix arithmetic (MMA) operations.

## -enum-fields

### -field D3D12DDI_WAVE_MMA_TIER_NOT_SUPPORTED:0

The driver doesn't support WaveMMA operations.

### -field D3D12DDI_WAVE_MMA_TIER_0_5_EXPERIMENTAL:5

The driver supports experimental WaveMMA operations.

## -remarks

For more information, see [Wave MMA](https://microsoft.github.io/DirectX-Specs/d3d/HLSL_SM_6_x_WaveMatrix.html).

## -see-also

[**D3D12DDI_SHADER_CAPS_0084**](ns-d3d12umddi-d3d12ddi_shader_caps_0084.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
