---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0** structure contains the input sequence and picture control parameters for a video encode operation.

## -struct-fields

### -field SequenceControlDesc

A [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md) structure that defines the configuration for the video sequence.

### -field PictureControlDesc

A [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md) structure that defines the configuration for the video picture.

### -field hDrvInputTexture2D

Handle to the the input frame to encode. This input frame is a D3D12 resource that can be consumed by other portions of the pipeline and therefore must not have the [**D3D12DDI_RESOURCE_FLAG_0080_VIDEO_ENCODE_REFERENCE_ONLY**](ne-d3d12umddi-d3d12ddi_resource_flags_0003.md) flag set.

### -field InputFrameSubresource

The sub-resource index for the **hDrvInputTexture2D** resource.

### -field CurrentFrameBitstreamMetadataSize

Number of bytes added to the final bitstream between the end of the last [**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) compressed bitstream output and the current call output. This member is intended to capture the size of any headers or metadata messages added by the client to the final bitstream. It is intended to be used as a hint by the rate control algorithms to keep track of the full bitstream size.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_output_stream_arguments_0080_2.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
