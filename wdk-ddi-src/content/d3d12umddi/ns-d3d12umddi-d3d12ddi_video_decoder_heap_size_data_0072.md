---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072
title: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072
ms.date: 03/24/2020
ms.assetid: 23b19cf9-5afc-4efb-92ee-2dc8c482ec6c
tech.root: display
ms.topic: language-reference
targetos: Windows
description: Retrieves the memory allocation size of a video decoder heap created with the given properties.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072
f1_keywords:
 - d3d12umddi//D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072
 - D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072
dev_langs:
 - c++
---

## -description

Retrieves the memory allocation size of a video decoder heap created with the given properties.

## -struct-fields

### -field NodeMask

For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field Configuration

A [**D3D12DDI_VIDEO_DECODE_CONFIGURATION**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md) structure with the decode profile and bitstream encryption.

### -field DecodeWidth

The decode width of the bitstream to be decoded.

### -field DecodeHeight

The decode height of the bitstream to be decoded.

### -field Format

The resource data format.

### -field FrameRate

The frame rate of the input video stream.

### -field BitRate

The bits per second data compression rate for the compressed video stream.

### -field MaxDecodePictureBufferCount

The maximum number of decode picture buffers that this stream can have.

### -field Protected

If TRUE, the decoder is created with a protected resource session and used with protected resources.

### -field MemoryPoolL0Size

The L0 size of the heap object. Memory Pool L0 is the memory pool “closest” to the GPU. In the case of UMA adapters, this is the amount of system memory used. For discrete adapters, this is the amount of discrete memory used.

### -field MemoryPoolL1Size

The L1 size of the heap object. Memory Pool L1 is the memory pool “second closest” to the GPU. In the case of UMA adapters, this value is zero. In the case of discrete adapters, this is the amount of system memory used.

## -remarks

This structure is for the D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE capability check in [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDI_VIDEO_DECODE_CONFIGURATION**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md)

[D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md)
