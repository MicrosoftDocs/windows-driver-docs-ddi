---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0** structure contains configuration information for an HEVC (H.265) codec.

## -struct-fields

### -field ConfigurationFlags

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_flags_0082_0.md) value that defines the set of enabled features. Flags can be combined.

### -field MinLumaCodingUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_CUSIZE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_cusize_0080.md) value that indicates the minimum luma coding block size to be used in the encoder. This value matches the value coded by the user in the Sequence Parameter Set (SPS).

### -field MaxLumaCodingUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_CUSIZE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_cusize_0080.md) value that indicates the maximum luma coding block size to be used in the encoder. This value matches the value coded by the user in the SPS.

### -field MinLumaTransformUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_TUSIZE_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_tusize_0082_0.md) value that indicates the minimum luma transform block size to be used in the encoder. This value matches the pixel size coded by the user in *SPS.log2_min_luma_transform_block_size_minus2*.

### -field MaxLumaTransformUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_TUSIZE_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_tusize_0082_0.md) value that indicates the maximum luma transform block size to be used in the encoder. This value must be consistent with the pixel size coded by the user in *SPS.log2_diff_max_min_luma_transform_block_size*. The variable *MaxTbLog2SizeY* is set equal to ```log2_min_luma_transform_block_size_minus2 + 2 + log2_diff_max_min_luma_transform_block_size```.

### -field max_transform_hierarchy_depth_inter

Indicates for the associated encoder, the maximum hierarchy depth for transform units of coding units coded in inter prediction mode. The value of **max_transform_hierarchy_depth_inter** must be in the range of 0 to ```CtbLog2SizeY − MinTbLog2SizeY```, inclusive. The value of **max_transform_hierarchy_depth_inter** must be consistent with the user-coded SPS headers.

### -field max_transform_hierarchy_depth_intra

Indicates for the associated encoder, the maximum hierarchy depth for transform units of coding units coded in intra prediction mode. The value of **max_transform_hierarchy_depth_intra** must be in the range of 0 to ```CtbLog2SizeY − MinTbLog2SizeY```, inclusive. The value of **max_transform_hierarchy_depth_intra** must be consistent with the user-coded SPS headers.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0082_0.md)
