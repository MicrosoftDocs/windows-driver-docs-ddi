---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2
---

## -description

The **D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2** structure contains the parameters for the output of a video encode operation.

## -struct-fields

### -field CompressedBitstream

A [**D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_compressed_bitstream_0080.md) structure that encapsulates the compressed bitstream output for the encoding operation.

### -field ReconstructedPicture

A [**D3D12DDI_VIDEO_ENCODE_RECONSTRUCTED_PICTURE_0080**](ns-d3d12umddi-d3d12ddi_video_encode_reconstructed_picture_0080.md) structure that encapsulates the reconstructed picture generated from the input frame passed to the encode operation. This resource is only needed if the encoded picture is marked to be used as a reference picture in the corresponding [picture control structure](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_0082_0.md) for this encode operation. Otherwise, this member can be set to NULL because the reconstructed picture will not be written in the output.

### -field HWLayoutEncoderMetadataDrvBuffer

A [**D3D12DDI_VIDEO_ENCODER_ENCODE_OPERATION_METADATA_BUFFER_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_encode_operation_metadata_buffer_0080_2.md) structure that contains metadata returned by the encoder regarding the hardware-specific layout of the output. This data needs to be resolved into a readable format using [**PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0**](PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0).

## -remarks

Check for alignment requirements for the output resources used for the encoding operation.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_INPUT_STREAM_ARGUMENTS_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_input_stream_arguments_0082_0.md)

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0**](PFND3D12DDI_VIDEO_ENCODE_RESOLVE_OUTPUT_METADATA_0082_0)
