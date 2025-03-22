---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
title: D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 (d3d12umddi.h)
description: Learn more about the D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 enumeration.
ms.date: 05/20/2024
keywords: ["D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 enumeration"]
ms.keywords: D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020, D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_INVERSE_QUANTIZATION_MATRIX, D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_PICTURE_PARAMETERS, D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_SLICE_CONTROL, d3d12umddi/D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_INVERSE_QUANTIZATION_MATRIX, d3d12umddi/D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_PICTURE_PARAMETERS, d3d12umddi/D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_SLICE_CONTROL, display.d3d12ddi_video_decode_parameter_type
req.header: d3d12umddi.h
req.construct-type: enumeration
req.include-header: D3d12umddi.h
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
req.typenames: D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
f1_keywords:
 - D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
 - d3d12umddi/D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
---

# D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 enumeration (d3d12umddi.h)



## -description

The **D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020** enumeration identifies the type of data that[**D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020->pData**](ns-d3d12umddi-d3d12ddi_video_decode_frame_argument_0020.md)

Contains the video decode parameter type.

## -enum-fields

### -field D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_PICTURE_PARAMETERS

Picture decoding parameter buffer.

### -field D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_INVERSE_QUANTIZATION_MATRIX

Inverse quantization matrix buffer.

### -field D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_SLICE_CONTROL

The slice-level parameters of a slice of bitstream data, for off-host bitstream compressed picture decoding.

### -field D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0097_HUFFMAN_TABLE

**pData** points to a Huffman table buffer.

## -remarks

The definition of each buffer type is dependent upon the decode profile and is defined in each codec specification.

## -see-also

[**D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020**](ns-d3d12umddi-d3d12ddi_video_decode_frame_argument_0020.md)
