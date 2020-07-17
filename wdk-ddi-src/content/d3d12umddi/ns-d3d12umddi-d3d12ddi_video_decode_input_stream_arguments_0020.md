---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
title: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 (d3d12umddi.h)
description: Specifies input stream arguments.
old-location: display\d3d12ddi_video_decode_input_stream_arguments.htm
ms.assetid: B956626C-B5D7-4217-A90A-EC7E436DF6C0
ms.date: 05/10/2018
keywords: ["D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020, D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS, display.d3d12ddi_video_decode_input_stream_arguments
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020"
 - "D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
---

# D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure


## -description


Specifies input stream arguments.


## -struct-fields




### -field FrameArguments

The arguments to decode each frame.


### -field FrameArgumentsCount

The count of frame arguments.


### -field ReferenceFrames

The reference frames needed for decoding this frame.  For more information, see the <a href="https://msdn.microsoft.com/B7ED4ADA-572A-4D15-B8FD-6EAF2DB87157">D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES</a> structure.


### -field CompressedBitstream

The compressed bitstream.  All source video slices should be placed contiguously, one after another, in this buffer.  For more information, see the <a href="https://msdn.microsoft.com/24A1D8C7-E432-45CB-8DEA-C1137159E319">D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM</a> structure.


### -field DecryptionParameters

Decryption parameters.  When decryption is not used, this structure is zero initialized.





## -see-also




<a href="https://msdn.microsoft.com/24A1D8C7-E432-45CB-8DEA-C1137159E319">D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM</a>



<a href="https://msdn.microsoft.com/B7ED4ADA-572A-4D15-B8FD-6EAF2DB87157">D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES</a>
 

 

