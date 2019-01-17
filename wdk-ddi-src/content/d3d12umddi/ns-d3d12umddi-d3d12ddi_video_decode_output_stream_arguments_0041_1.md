---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1
title: D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1
description: Output stream arguments for video decode.
ms.assetid: 97cff37b-60b5-45b4-8e73-c19187c46e9e
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1, D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1,
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
req.typenames: D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1 structure

## -description

Output stream arguments for video decode.

## -struct-fields

### -field hDrvOutputTexture2D

The output texture. If decode conversion is enabled, this output specifies the post conversion output. If decode conversion is not enabled, this is the decode output.

### -field OutputSubresource

The output subresource to use for the <i>hDrvOutputTexture2D</i> parameter. If the output is an array, this allows specifying array indices.

### -field ConversionArguments

Optional output conversion arguments.

### -field Histograms

An array of D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041 structures.

