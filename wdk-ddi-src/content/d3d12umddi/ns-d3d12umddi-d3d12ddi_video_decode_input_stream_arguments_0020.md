---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
title: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020
author: windows-driver-content
description: Specifies input stream arguments.
old-location: display\d3d12ddi_video_decode_input_stream_arguments.htm
old-project: display
ms.assetid: B956626C-B5D7-4217-A90A-EC7E436DF6C0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS, display.d3d12ddi_video_decode_input_stream_arguments, D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure [Display Devices]
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
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
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

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_compressed_bitstream_0020.md">D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM</a>

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_reference_frames_0020.md">D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

