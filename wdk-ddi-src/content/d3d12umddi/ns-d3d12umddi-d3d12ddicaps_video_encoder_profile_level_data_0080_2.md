---
UID: NS:d3d12umddi.D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2
tech.root: display
title: D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2 structure.
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
req.typenames: D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2
f1_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2
 - d3d12umddi/D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2
---

## -description

The **D3D12DDICAPS_VIDEO_ENCODER_PROFILE_LEVEL_DATA_0080_2** structure is used to check whether the adapter supports the specified profile for video encoding and return the supported levels range for that profile.

## -struct-fields

### -field NodeIndex

[in] In a multi-adapter operation, **NodeIndex** indicates which physical adapter of the device that the operation applies to.

### -field Codec

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that specifies the codec to check support for.

### -field Profile

[in] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that specifies the profile to check support for.

### -field IsSupported

[out] Indicates whether the adapter supports the specified **Profile**.

### -field MinSupportedLevel

[out] A [**D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_level_setting_0080_2.md) structure in which the minimum supported level for the selected codec and profile is returned, if supported.

### -field MaxSupportedLevel

[out] A [**D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_level_setting_0080_2.md) structure in which the maximum supported level for the selected codec and profile is returned, if supported.

## -remarks

The D3D runtime calls [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) with [**D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_PROFILE_LEVEL**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) specified as the capability type.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)
