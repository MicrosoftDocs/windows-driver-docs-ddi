---
UID: NS:d3d12umddi.D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2
tech.root: display
title: D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2 structure.
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
req.typenames: D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2
f1_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2
 - d3d12umddi/D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2
---

## -description

The **D3D12DDICAPS_VIDEO_ENCODER_RESOURCE_REQUIREMENTS_DATA_0080_2** structure specifies resource access requirements.

## -struct-fields

### -field NodeIndex

[in] In a multi-adapter operation, **NodeIndex** indicates which physical adapter of the device that the operation applies to.

### -field Codec

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that specifies the codec to check support for.

### -field Profile

[in] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that specifies the profile to check support for.

### -field InputFormat

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) value that specifies the input format of the input frames.

### -field PictureTargetResolution

[in] A [**D3D12DDI_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_resolution_desc_0080.md) structure that indicates the picture resolution for which resource requirements are being queried.

### -field IsSupported

[out] Indicates whether the given input values are supported.

### -field CompressedBitstreamBufferAccessAlignment

[out] Indicates the alignment required in bytes for the resource to be passed in the **hDrvBuffer** and **Offset** members of [**D3D12DDI_VIDEO_ENCODER_COMPRESSED_BITSTREAM_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_compressed_bitstream_0080.md). If no alignment is required, the driver should report 1 to indicate 1 byte (trivial) alignment.

### -field EncoderMetadataBufferAccessAlignment

[out] Indicates the alignment required in bytes for the resource to be passed in [**D3D12DDI_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_STREAM_ARGUMENTS_0080_2.HWLayoutEncoderMetadataDrvBuffer**](ns-d3d12umddi-d3d12ddi_video_encoder_encodeframe_output_stream_arguments_0080_2.md). If no alignment is required, the driver should report 1 to convey 1 byte (trivial) alignment.

### -field MaxEncoderOutputMetadataBufferSize

[out] Indicates the maximum size in bytes needed for the resource that will be allocated by the host and used as output in [**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) for output encoder metadata based on the input arguments.

## -remarks

The D3D runtime calls [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) with [**D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_RESOURCE_REQUIREMENTS**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) specified as the capability type.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)
