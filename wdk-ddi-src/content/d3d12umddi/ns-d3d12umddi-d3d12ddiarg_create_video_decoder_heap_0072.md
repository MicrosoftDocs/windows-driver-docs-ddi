---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072
title: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072
ms.date: 03/24/2020
ms.topic: language-reference
ms.assetid: 05213823-cca6-4e98-b074-b78557fdaaf2
tech.root: display
targetos: Windows
description: Structure used to create a video decoder heap for a decode session.
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072
f1_keywords:
 - d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0072
dev_langs:
 - c++
---

## -description

Structure used to create a video decoder heap for a decode session.

## -struct-fields

### -field NodeMask

For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field Configuration

The decode profile and bitstream encryption. See [**D3D12DDI_VIDEO_DECODE_CONFIGURATION**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md).

### -field DecodeWidth

The width of the bitstream to be decoded.

### -field DecodeHeight

The height of the bitstream to be decoded.

### -field Format

The resource data format.

### -field FrameRate

The frame rate of the input video stream.

### -field BitRate

The bits per second data compression rate for the compressed video stream.

### -field MaxDecodePictureBufferCount

The maximum number of decode picture buffers this stream can have.

### -field hDrvProtectedResourceSession

Handle to the protected resource session acquired at object creation time.

## -remarks

The decoder heap holds the allocations for a decode session, and may contain state including reference related data such as motion vectors. In the event of a resolution change or a **MaxDecodePictureBufferCount** change, a new instance of this object is created. It is codec specific when these properties can change.

The decode width and height specify the native stream resolution before any scale. The maximum Decode Picture Buffer (DPB) count specifies the largest DPB count that can be used without recreating the video decode stream.

The Bitrate and FrameRate parameters may be used by drivers to inform heuristics such as intermediate allocation sizes or performance optimizations.

Decoding a frame can fail if the Bitrate and FrameRate values are insufficient for the video stream.  If decode fails for this reason, the query D3D12DDI_QUERY_TYPE_VIDEO_DECODE_STATISTICS must return Status D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED.

The Bitrate and FrameRate parameters may also be set to zero.  When these values are used, drivers must make worst case assumptions and are not allowed to fail with D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED.

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDI_VIDEO_DECODE_CONFIGURATION**](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md)
