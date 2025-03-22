---
UID: NE:d3d10umddi.D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE
title: D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE (d3d10umddi.h)
description: Learn more about D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE enumeration.
ms.date: 05/20/2024
keywords: ["D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE enumeration"]
ms.keywords: D3D11_1DDI_VIDEO_DECODER_BUFFER_BITSTREAM, D3D11_1DDI_VIDEO_DECODER_BUFFER_DEBLOCKING_CONTROL, D3D11_1DDI_VIDEO_DECODER_BUFFER_FILM_GRAIN, D3D11_1DDI_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX, D3D11_1DDI_VIDEO_DECODER_BUFFER_MACROBLOCK_CONTROL, D3D11_1DDI_VIDEO_DECODER_BUFFER_MOTION_VECTOR, D3D11_1DDI_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS, D3D11_1DDI_VIDEO_DECODER_BUFFER_RESIDUAL_DIFFERENCE, D3D11_1DDI_VIDEO_DECODER_BUFFER_SLICE_CONTROL, D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE, D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE enumeration [Display Devices], D3D11_1DDI_VIDEO_DECODER_BUFFER_UNKNOWN, D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE, D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_BITSTREAM, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_DEBLOCKING_CONTROL, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_FILM_GRAIN, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_MACROBLOCK_CONTROL, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_MOTION_VECTOR, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_RESIDUAL_DIFFERENCE, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_SLICE_CONTROL, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_UNKNOWN, d3d10umddi/D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE, display.d3d11_ddi_video_decoder_buffer_type
req.header: d3d10umddi.h
req.construct-type: enumeration
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE
f1_keywords:
 - D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE
 - d3d10umddi/D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE
 - D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE
 - d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE
 - D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE
---

# D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE enumeration (d3d10umddi.h)



## -description

The **D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE** enumeration indicates the type of buffer used by a D3D11 video decoder.

## -enum-fields

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_UNKNOWN:0

An unknown buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_PICTURE_PARAMETERS:1

Picture parameters decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_MACROBLOCK_CONTROL:2

Macroblock control command decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_RESIDUAL_DIFFERENCE:3

Residual block difference decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_DEBLOCKING_CONTROL:4

Deblocking filter control command decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_INVERSE_QUANTIZATION_MATRIX:5

Inverse-quantization matrix decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_SLICE_CONTROL:6

Slice-control decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_BITSTREAM:7

Bitstream data decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_MOTION_VECTOR:8

Motion-vector decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_FILM_GRAIN:9

Film-grain decode compressed buffer format.

### -field D3D11_1DDI_VIDEO_DECODER_BUFFER_HUFFMAN_TABLE:10

The buffer format is Huffman tables.

## -remarks

Note that the **D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE** and **D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE** enumerations are defined as the same type.

## -see-also

[**D3D11DDIARG_CREATERESOURCE**](ns-d3d10umddi-d3d11ddiarg_createresource.md)
