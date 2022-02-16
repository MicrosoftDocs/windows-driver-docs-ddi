---
UID: NS:d3d12umddi.D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0
tech.root: display
title: D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0 structure.
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
req.typenames: D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0
f1_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0
 - d3d12umddi/D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0
dev_langs:
 - c++
---

## -description

The **D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0** structure provides support details for the passed input configurations.

## -struct-fields

### -field NodeIndex

[in] In a multi-adapter operation, **NodeIndex** indicates which physical adapter of the device that the operation applies to.

### -field Codec

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that specifies the encode codec to use.

### -field InputFormat

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) value that specifies the input format of the input frames.

### -field CodecConfiguration

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0082_0.md) structure that specifies the requested configuration for the selected codec. The codec-specific structure within this structure should match the codec type specified by **Codec**.

### -field CodecGopSequence

[in] A [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_gop_structure_0082_0.md) structure that specifies the requested group of pictures (GOP) configuration for the selected codec. The codec-specific structure within this structure should match the codec type specified by **Codec**.

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

### -field MaxReferenceFramesInDPB

[in] The maximum number of previous reference frames to be used when calling [**EncodeFrame**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) for inter-frames. This value is used to calculate the suggested level.

### -field ValidationFlags

[out] A [**D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_validation_flags_0082_0.md) value that provides more details if the cap query returns with the[**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_GENERAL_SUPPORT_OK**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md) bit not set.

### -field SupportFlags

[out] A [**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md) value that specifies the support details for the requested configuration.

### -field SuggestedProfile

[out] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure in which the driver returns the matching profile for the requested configuration.

### -field SuggestedLevel

[out] A [**D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_level_setting_0080_2.md) structure in which the driver returns the matching level for the requested configuration for each resolution present in **pResolutionList**.

### -field pResolutionDependentSupport

[out] Pointer to a list of [**D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md) structures in which the driver returns the resolution-dependent support limits.

## -remarks

The D3D runtime calls [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) with [**D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_SUPPORT**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) specified as the capability type.

The support granted or rejected by this query indicates simultaneous support for all the features selected to be used in the same encoding session. There can be features that are supported individually when queried with individual query calls but not supported simultaneously.

For example, there can be support for intra refresh when checking **D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_INTRA_REFRESH_MODE** and there can be support for B frames when checking that [**D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL1ReferencesForB**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_picture_control_support_h264_0080_2.md) is greater than 0. However, there can be the case that intra refresh and B frames are not supported simultaneously. In this case, querying **D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_SUPPORT** with **CodecGopSequence** containing B frames and intra refresh row-based mode, the D3D12_VIDEO_ENCODER_SUPPORT_FLAG_GENERAL_SUPPORT_OK flag must be set off.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
