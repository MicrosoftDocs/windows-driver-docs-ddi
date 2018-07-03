---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
title: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
author: windows-driver-content
description: Create a video decoder heap.
old-location: display\d3d12ddiarg-create-video-decoder-heap-0033.htm
old-project: display
ms.assetid: 158411ee-6cc1-466d-b772-fe380b55baef
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033, D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033, display.d3d12ddiarg-create-video-decoder-heap-0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header:
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
product:
- Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
---

# D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 structure


## -description


Used to create a decoder object for a decode session.


## -struct-fields




### -field NodeMask

For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.


### -field Configuration

The decode profile and bitstream encryption.  See D3D12DDI_VIDEO_DECODE_CONFIGURATION.


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

The maximum number of decode picture buffers this stream can have.

## -remarks

The decoder heap holds the allocations for a decode session, and may contain state including reference related data such as motion vectors. In the event of a resolution change or a MaxDecodePictureBufferCount change, a new instance of this object is created. It is codec specific when these properties can change.

The decode width and height specify the native stream resolution before any scale. The maximum Decode Picture Buffer (DPB) count specifies the largest DPB count that can be used without recreating the video decode stream.

The Bitrate and FrameRate parameters may be used by drivers to inform heuristics such as intermediate allocation sizes or performance optimizations.

Decoding a frame can fail if the Bitrate and FrameRate values are insufficient for the video stream.  If decode fails for this reason, the query D3D12DDI_QUERY_TYPE_VIDEO_DECODE_STATISTICS must return Status D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED.

The Bitrate and FrameRate parameters may also be set to zero.  When these values are used, drivers must make worst case assumptions and are not allowed to fail with D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED.
