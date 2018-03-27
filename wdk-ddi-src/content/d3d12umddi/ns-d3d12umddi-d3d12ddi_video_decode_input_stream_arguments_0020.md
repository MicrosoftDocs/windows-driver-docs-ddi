---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
title: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
author: windows-driver-content
description: Specifies input stream arguments.
old-location: display\d3d12ddi_video_decode_input_stream_arguments.htm
old-project: display
ms.assetid: B956626C-B5D7-4217-A90A-EC7E436DF6C0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020, D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS, display.d3d12ddi_video_decode_input_stream_arguments
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
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
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
---

# D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure


## -description


Specifies input stream arguments.


## -syntax


````
typedef struct D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 {
  D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020       FrameArguments[D3D12DDI_VIDEO_DECODE_MAX_ARGUMENTS_0020];
  UINT                                            FrameParametersCount;
  D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0020     ReferenceFrames;
  D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020 CompressedBitstream;
  D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0020 DecryptionParameters;
} D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020;
````


## -struct-fields




### -field FrameArguments

The arguments to decode each frame.


### -field FrameArgumentsCount




### -field ReferenceFrames

The reference frames needed for decoding this frame.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_reference_frames_0020.md">D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES</a> structure.


### -field CompressedBitstream

The compressed bitstream.  All source video slices should be placed contiguously, one after another, in this buffer.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_compressed_bitstream_0020.md">D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM</a> structure.


### -field DecryptionParameters

Decryption parameters.  When decryption is not used, this structure is zero initialized.


#### - FrameParametersCount

The count of frame arguments.


## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_reference_frames_0020.md">D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_compressed_bitstream_0020.md">D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM</a>



 

 


