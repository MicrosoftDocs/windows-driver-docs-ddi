---
UID: NE:d3d12umddi.D3D12DDI_WAVE_MMA_ACCUM_DATATYPE
tech.root: display
title: D3D12DDI_WAVE_MMA_ACCUM_DATATYPE
ms.date: 05/06/2024
targetos: Windows
description: Learn about the D3D12DDI_WAVE_MMA_ACCUM_DATATYPE enumeration.
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
 - D3D12DDI_WAVE_MMA_ACCUM_DATATYPE
f1_keywords:
 - D3D12DDI_WAVE_MMA_ACCUM_DATATYPE
 - d3d12umddi/D3D12DDI_WAVE_MMA_ACCUM_DATATYPE
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WAVE_MMA_ACCUM_DATATYPE
---

# D3D12DDI_WAVE_MMA_ACCUM_DATATYPE enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_WAVE_MMA_ACCUM_DATATYPE** enumeration is a bitwise-OR of the data types supported for the accumulator in a matrix-multiply-accumulate (MMA) operation.

## -enum-fields

### -field D3D12DDI_WAVE_MMA_ACCUM_DATATYPE_NONE:0

The accumulator data type is not specified.

### -field D3D12DDI_WAVE_MMA_ACCUM_DATATYPE_INT32:0x1

The driver supports 32-bit integer data.

### -field D3D12DDI_WAVE_MMA_ACCUM_DATATYPE_FLOAT16:0x2

The driver supports 16-bit floating-point data.

### -field D3D12DDI_WAVE_MMA_ACCUM_DATATYPE_FLOAT:0x4

The driver supports 32-bit floating-point data.

## -remarks

For more information, see [Wave MMA](https://microsoft.github.io/DirectX-Specs/d3d/HLSL_SM_6_x_WaveMatrix.html).

## -see-also

[**D3D12DDI_WAVE_MMA_DATA_0103**](ns-d3d12umddi-d3d12ddi_wave_mma_data_0103.md)
