---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095
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
 - D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095** structure contains configuration support parameters for AV1 encoding.

## -struct-fields

### -field SupportedFeatureFlags

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_feature_0095_flags.md) enumeration that indicates which features are supported for the codec. Supported features can be set or not by the API Client.

### -field RequiredFeatureFlags

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_FEATURE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_feature_0095_flags.md) enumeration that indicates which features the driver requires to be set by the API Client.

### -field SupportedInterpolationFilters

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_interpolation_filters_0095_flags.md) enumeration that indicates which values can be selected as input parameters of type [**D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_interpolation_filters_0095.md).

### -field SupportedRestorationParams[3]

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_restoration_support_0095_flags.md) enumeration that indicates which values can be selected as input parameters for **FrameRestorationType** and **LoopRestorationPixelSize** in [**D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_restoration_config_0095.md).

The first array indexing corresponds to the restoration filter type.

| Index i in SupportedRestorationParams[i][j] | Filter type |
|--------------------------------------------|-------------|
| 0 | SWITCHABLE |
| 1 | WIENER |
| 2 | SGRPROJ |

Note the indexing of the filter types corresponds to D3D12_VIDEO_ENCODER_AV1_RESTORATION_TYPE minus 1 (skipping D3D12_VIDEO_ENCODER_AV1_RESTORATION_TYPE_DISABLED).

The second array indexing corresponds to the planes.

| Index j in SupportedRestorationParams[i][j] | Plane |
| ------------------------------------------- | ----- |
| 0 | Y plane |
| 1 | U plane |
| 2 | V plane |

The value returned in SupportedRestorationParams[i][j] is a bitflag mask indicating whether the i-th filter in the j-th plane is either:

* Not supported indicated by SupportedRestorationParams[i][j] = D3D12_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_FLAG_NOT_SUPPORTED.
* Supported with any of the D3D12_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE as indicated by the combinable bit flags in SupportedRestorationParams[i][j].

### -field SupportedSegmentationModes

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_mode_0095_flags.md) enumeration that indicates which segmentation modes can be selected in [**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_config_0095.md).

### -field SupportedTxModes[4]

Output parameter. An array of [**D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_tx_mode_0095_flags.md) values that indicates which transform mode values can be selected as input parameters of type [**D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_tx_mode_0095.md) for each different [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095.md). The driver must support at least 1 mode for each frame type; that is, the mask value can't be 0.

### -field SegmentationBlockSize

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_BLOCK_SIZE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_block_size_0095.md) enumeration that indicates the block size for the segment map. This is both for the input blocks in [**D3D12_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_map_0095.md) for custom segmentation or the block size of the segment map written in the compressed bitstream by the driver in auto segmentation.

### -field PostEncodeValuesFlags

A [**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095_flags.md) enumeration that specifies which AV1 encoding features the underlying encoder is able to override the associated AV1 syntax values for or accept API Client configurable input exactly.

### -field MaxTemporalLayers

Specifies the maximum number of temporal layers that can be supported. The reported values must be in the range [1..MaxTemporalIdSupported + 1]. A reported value 1, there is no temporal scalability support.

### -field MaxSpatialLayers

Specifies the maximum number of spatial layers that can be supported. The reported values must be in the range [1..MaxSpatialIdSupported + 1]. A reported value 1, there is no spatial scalability support.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_codec_configuration_support_data_0083_0.md)
