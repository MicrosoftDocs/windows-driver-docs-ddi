---
UID: NS:d3d12umddi.D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095
tech.root: display
title: D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095
f1_keywords:
 - D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095
 - d3d12umddi/D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095
---

# D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095 structure (d3d12umddi.h)

## -description

The **D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095** structure describes support for the video encoder frame subregion layout configuration, particularly for the AV1 codec.

## -struct-fields

### -field NodeIndex

[in] In a multi-adapter operation, **NodeIndex** indicates which physical adapter of the device that the operation applies to.

### -field Codec

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) enumeration that represents the desired codec to check support for.

### -field Profile

[in] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_02**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that describes the desired profile to check support for.

### -field Level

[in] A [**D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_level_setting_0080_2.md) structure that describes the desired level to check support for.

### -field SubregionMode

[in] A [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md) enumeration that specifies the desired frame subregion layout mode to check support for.

### -field FrameResolution

[in] A [**D3D12DDI_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_resolution_desc_0080.md) structure that describes the desired resolution to check support for.

### -field CodecSupport

[in/out] A [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_config_support_0095.md) structure that describes the codec-specific support for this capability.

### -field IsSupported

[out] A Boolean value that indicates whether the driver supports this subregion layout configuration based on the input values, including the codec, profile, level, resolution and any other codec specific parameters.

## -remarks

Currently, this support query is only supported for **Codec** set to D3D12DDI_VIDEO_ENCODER_CODEC_0095_AV1, as it can only be compiled with a **CodecSupport.pAV1Support** pointer of type [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_frame_subregion_layout_config_support_0095.md).

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.
