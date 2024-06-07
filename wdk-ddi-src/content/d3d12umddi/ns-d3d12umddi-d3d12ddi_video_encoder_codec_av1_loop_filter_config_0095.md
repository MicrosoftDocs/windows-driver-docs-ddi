---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095
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
 - D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_AV1_LOOP_FILTER_CONFIG_0095** structure describes the loop filter configuration for the AV1 encoder.

## -struct-fields

### -field LoopFilterLevel[2]

Related to AV1 syntax loop_filter_level[0], loop_filter_level[1].

### -field LoopFilterLevelU

Related to AV1 syntax loop_filter_level[2].

### -field LoopFilterLevelV

Related to AV1 syntax loop_filter_level[3].

### -field LoopFilterSharpnessLevel

Related to AV1 syntax loop_filter_sharpness.

### -field LoopFilterDeltaEnabled

Related to AV1 syntax loop_filter_delta_enabled. Requires that[**D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAG_LOOP_FILTER_DELTAS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_feature_0095_flags.md) be supported/enabled.

### -field UpdateRefDelta

Related to AV1 syntax update_ref_delta.

### -field RefDeltas[8]

Related to AV1 syntax loop_filter_ref_deltas.

### -field UpdateModeDelta

Related to AV1 syntax update_mode_delta.

### -field ModeDeltas[2]

Related to AV1 syntax loop_filter_mode_deltas.

## -remarks

AV1 syntax loop_filter_delta_update is derived from members as (**UpdateRefDelta** || **UpdateModeDelta**).

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_feature_0095_flags.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095.md)
