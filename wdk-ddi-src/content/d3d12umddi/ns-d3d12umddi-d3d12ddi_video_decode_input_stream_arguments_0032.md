---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032
title: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 (d3d12umddi.h)
description: Video decode input stream arguments.
old-location: display\d3d12ddi-video-decode-input-stream-arguments-0032.htm
ms.assetid: ca647cd3-357b-4cd6-aa1c-6a03d5a77f10
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032, D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032, display.d3d12ddi-video-decode-input-stream-arguments-0032
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032
---

# D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 structure


## -description


Video decode input stream arguments.


## -struct-fields




### -field FrameArguments

The arguments to decode each frame.


### -field NumFrameArguments

The count of frame arguments.


### -field ReferenceFrames

The reference frames needed for decoding this frame. See [D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES](ns-d3d12umddi-d3d12ddi_video_decode_reference_frames_0032.md).


### -field CompressedBitstream

The compressed bitstream. All source video slices should be placed contiguously (one after another) in this buffer.  See [D3D12DDI_VIDEO_COMPRESSED_BITSTREAM](ns-d3d12umddi-d3d12ddi_video_decode_compressed_bitstream_0032.md).


### -field DecryptionParameters

Decryption parameters. When decryption is not used, this structure is zero initialized. See [D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS](ns-d3d12umddi-d3d12ddi_video_decode_decryption_arguments_0030.md).


### -field hDrvVideoDecoderHeap

Supplies allocations that may contain the state for the current decode operation.

