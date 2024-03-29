---
UID: NS:d3d12umddi.D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0
tech.root: display
title: D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0 structure.
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
req.typenames: D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0
f1_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0
 - d3d12umddi/D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0082_0** structure is used to indicate whether the specified input HEVC codec configuration parameters are supported or retrieves (outputs) the supported configuration for H.264 encoding.

## -struct-fields

### -field NodeIndex

[in] In a multi-adapter operation, **NodeIndex** indicates which physical adapter of the device that the operation applies to.

### -field Codec

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that specifies the codec to check support for.

### -field Profile

[in] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that specifies the profile to check support for.

### -field IsSupported

[out] Indicates whether the given feature values are supported.

### -field CodecSupportLimits

[in/out] A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_0082_0.md) structure:

* For H.264 encoding, this structure is used as an output parameter in which the driver writes the support configuration limits.
* For HEVC encoding, this structure contains input parameters with the user-requested HEVC configuration.

## -remarks

Use [**D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_codec_configuration_support_data_0083_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).

## -see-also

[**D3D12DDICAPS_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_codec_configuration_support_data_0083_0.md)
