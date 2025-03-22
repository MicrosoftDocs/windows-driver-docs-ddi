---
UID: NE:d3d12umddi.D3D12DDI_WAVE_MMA_DIMENSION
tech.root: display
title: D3D12DDI_WAVE_MMA_DIMENSION
ms.date: 05/06/2024
targetos: Windows
description: Learn about the D3D12DDI_WAVE_MMA_DIMENSION enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
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
 - D3D12DDI_WAVE_MMA_DIMENSION
f1_keywords:
 - D3D12DDI_WAVE_MMA_DIMENSION
 - d3d12umddi/D3D12DDI_WAVE_MMA_DIMENSION
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WAVE_MMA_DIMENSION
---

# D3D12DDI_WAVE_MMA_DIMENSION enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_WAVE_MMA_DIMENSION** enumeration specifies a dimension for a matrix being used for wave-based matrix multiply-accumulate (MMA) operations.

## -enum-fields

### -field D3D12DDI_WAVE_MMA_DIMENSION_INVALID

Indicates an invalid or unsupported dimension.

### -field D3D12DDI_WAVE_MMA_DIMENSION_16

Indicates a dimension size of 16.

### -field D3D12DDI_WAVE_MMA_DIMENSION_64

Indicates a dimension size of 64.

## -remarks

For more information, see [Wave MMA](https://microsoft.github.io/DirectX-Specs/d3d/HLSL_SM_6_x_WaveMatrix.html).

## -see-also

[**D3D12DDI_WAVE_MMA_DATA_0103**](ns-d3d12umddi-d3d12ddi_wave_mma_data_0103.md)
