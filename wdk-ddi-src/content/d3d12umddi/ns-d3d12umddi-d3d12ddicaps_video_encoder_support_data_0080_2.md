---
UID: NS:d3d12umddi.D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2
tech.root: display
title: D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2 structure. 
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
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2
f1_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2
 - d3d12umddi/D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2
dev_langs:
 - c++
---

## -description

The **D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0080_2** structure provides support details for the passed input configurations.

## -struct-fields

### -field NodeIndex

[in] In a multi-adapter operation, **NodeIndex** indicates which physical adapter of the device that the operation applies to.

### -field Codec

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that specifies the encode codec to use.

### -field TargetProfile

[in] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that specifies the requested profile configuration.

### -field TargetLevel

[in] A [**D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_level_setting_0080_2.md) structure that specifies the requested level setting.

### -field InputFormat

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) value that specifies the input format of the input frames.

### -field CodecConfiguration

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0080_2.md) structure that specifies the requested configuration for the selected codec. The codec-specific structure within this structure should match the codec type specified by **Codec**.

### -field RateControl

[in] A [**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_0080_2.md) structure that specifies the requested rate control configuration.

### -field IntraRefresh

[in] A [**D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_MODE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_intra_refresh_mode_0080.md) value that specifies the requested intra refresh mode.

### -field SubregionFrameEncoding

[in] A [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md) value that specifies the requested subregion partitioning mode.

### -field ResolutionsListCount

[in] Indicates the number of resolutions in the list that **pResolutionList** points to.

### -field pResolutionList

[in] Pointer to an array of [**D3D12DDI_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_resolution_desc_0080.md) structures that specifies the list of resolutions requested to be supported.

### -field ValidationFlags

[out] A [**D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_validation_flags_0080.md) value that provides more details if the cap query returns with the[**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0080_GENERAL_SUPPORT_OK**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0080.md) bit not set.

### -field SupportFlags

[out] A [**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0080.md) value that specifies the support details for the requested configuration.

### -field SuggestedProfile

[out] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure in which the driver returns the matching profile for the requested configuration.

### -field SuggestedLevel

[out] A [**D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_level_setting_0080_2.md) structure in which the driver returns the matching level for the requested configuration for each resolution present in **pResolutionList**.

### -field pResolutionDependentSupport

[out] Pointer to a list of [**D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md) structures in which the driver returns the resolution-dependent support limits.

## -remarks

Use [**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).

## -see-also

[**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md)
