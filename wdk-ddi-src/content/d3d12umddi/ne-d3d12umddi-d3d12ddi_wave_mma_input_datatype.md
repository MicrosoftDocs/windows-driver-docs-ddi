---
UID: NE:d3d12umddi.D3D12DDI_WAVE_MMA_INPUT_DATATYPE
tech.root: display
title: D3D12DDI_WAVE_MMA_INPUT_DATATYPE
ms.date: 05/06/2024
targetos: Windows
description: Learn more about the D3D12DDI_WAVE_MMA_INPUT_DATATYPE enumeration.
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
 - D3D12DDI_WAVE_MMA_INPUT_DATATYPE
f1_keywords:
 - D3D12DDI_WAVE_MMA_INPUT_DATATYPE
 - d3d12umddi/D3D12DDI_WAVE_MMA_INPUT_DATATYPE
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WAVE_MMA_INPUT_DATATYPE
---

# D3D12DDI_WAVE_MMA_INPUT_DATATYPE enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_WAVE_MMA_INPUT_DATATYPE** enumeration specifies the type of the input data for Direct3D matrix-multiply-accumulate (MMA) operations.

## -enum-fields

### -field D3D12DDI_WAVE_MMA_INPUT_DATATYPE_INVALID

Indicates an invalid input data type.

### -field D3D12DDI_WAVE_MMA_INPUT_DATATYPE_BYTE

Indicates that the input data type is a byte.

### -field D3D12DDI_WAVE_MMA_INPUT_DATATYPE_FLOAT16

Indicates that the input data type is a 16-bit floating-point value.

### -field D3D12DDI_WAVE_MMA_INPUT_DATATYPE_FLOAT

Indicates that the input data type is a 32-bit floating-point value.

## -remarks

For more information, see [Wave MMA](https://microsoft.github.io/DirectX-Specs/d3d/HLSL_SM_6_x_WaveMatrix.html).

## -see-also

[**D3D12DDI_WAVE_MMA_DATA_0103**](ns-d3d12umddi-d3d12ddi_wave_mma_data_0103.md)
