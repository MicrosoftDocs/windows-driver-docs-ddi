---
UID: NS:d3d12umddi.D3D12DDI_WAVE_MMA_DATA_0103
tech.root: display
title: D3D12DDI_WAVE_MMA_DATA_0103
ms.date: 05/06/2024
targetos: Windows
description: Learn about the D3D12DDI_WAVE_MMA_DATA_0103 structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_WAVE_MMA_DATA_0103
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
 - D3D12DDI_WAVE_MMA_DATA_0103
f1_keywords:
 - D3D12DDI_WAVE_MMA_DATA_0103
 - d3d12umddi/D3D12DDI_WAVE_MMA_DATA_0103
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WAVE_MMA_DATA_0103
---

# D3D12DDI_WAVE_MMA_DATA_0103 structure (d3d12umddi.h)

## -description

The **D3D12DDI_WAVE_MMA_DATA_0103** structure describes a driver's support for Direct3D matrix-multiply-accumulate (MMA) operations.

## -struct-fields

### -field InputDataType

[in] A [**D3D12DDI_WAVE_MMA_INPUT_DATATYPE**](ne-d3d12umddi-d3d12ddi_wave_mma_input_datatype.md) enumeration that specifies the type of the input data.

### -field M

[in] A [**D3D12DDI_WAVE_MMA_DIMENSION**](ne-d3d12umddi-d3d12ddi_wave_mma_dimension.md) enumeration that specifies the dimension of the matrix operation that corresponds to the number of rows in the left matrix.

### -field N

[in] A [**D3D12DDI_WAVE_MMA_DIMENSION**](ne-d3d12umddi-d3d12ddi_wave_mma_dimension.md) enumeration that specifies the dimension of the matrix operation that corresponds to the number of columns in the right matrix.

### -field Supported

[out] Set to TRUE if the hardware supports the specified matrix dimensions and data type; otherwise FALSE.

### -field K

[out] Specifies the shared dimension size supported by the device for the given combination of **M** and ((N)). This value must be an even multiple of 16.

### -field AccumDataTypes

[out] The [**D3D12DDI_WAVE_MMA_ACCUM_DATATYPE**](ne-d3d12umddi-d3d12ddi_wave_mma_accum_datatype.md) enumeration that specifies the supported accumulation data types.

### -field RequiredWaveLaneCountMin

[out] The minimum number of wave lanes required to support the wave MMA intrinsics.

### -field RequiredWaveLaneCountMax

[out] The maximum number of wave lanes that can be used to support the wave MMA intrinsics.

## -remarks

The matrix multiplication unit is defined by three dimensions **M**, **N**, and **K**. The matrix multiplication unit thus is defined to be a multiplication of two matrices of dimensions **MxK** (left matrix) and **KxN** (right matrix) with a resulting matrix of size **MxN**.

A hardware implementation can support only one **K** value for each combination of **M**, **N**, and **InputDataType**. The possible dimensions of **M** and **N** are restricted to the allowed enum values defined by [**D3D12DDI_WAVE_MMA_DIMENSION**](ne-d3d12umddi-d3d12ddi_wave_mma_dimension.md) **M** and **D3D12DDI_WAVE_MMA_DIMENSION** **N**. The K dimension is defined to be an even multiple of 16 provided by the driver through the D3D12_FEATURE_DATA_WAVE_MMA CheckFeatureSupport Caps. The **K** value is considered a constant and the driver should unroll loops using it, if possible.

For more information, see [Wave MMA](https://microsoft.github.io/DirectX-Specs/d3d/HLSL_SM_6_x_WaveMatrix.html).

## -see-also

[**D3D12DDI_WAVE_MMA_ACCUM_DATATYPE**](ne-d3d12umddi-d3d12ddi_wave_mma_accum_datatype.md)

[**D3D12DDI_WAVE_MMA_DIMENSION**](ne-d3d12umddi-d3d12ddi_wave_mma_dimension.md)

[**D3D12DDI_WAVE_MMA_INPUT_DATATYPE**](ne-d3d12umddi-d3d12ddi_wave_mma_input_datatype.md)
