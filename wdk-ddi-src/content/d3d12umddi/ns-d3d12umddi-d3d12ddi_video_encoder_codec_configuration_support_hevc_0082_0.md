---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0** structure contains user-requested HEVC configuration parameters for HEVC encoding.

## -struct-fields

### -field SupportFlags

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_hevc_flags_0082_0.md) value that indicates which optional feature(s) are requested for the codec.

### -field MinLumaCodingUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_CUSIZE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_cusize_0080.md) value that indicates the requested minimum luma coding block size. This value matches the value used by the user in the sequence parameter set (SPS).

### -field MaxLumaCodingUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_CUSIZE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_cusize_0080.md) value that indicates the requested maximum luma coding block size. This value matches the value used by the user in the sequence parameter set (SPS).

### -field MinLumaTransformUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_TUSIZE_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_tusize_0082_0.md) value that indicates the requested minimum luma transform block size. This value must be consistent with the pixel size coded by the user in *SPS.log2_min_luma_transform_block_size_minus2*.

### -field MaxLumaTransformUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_TUSIZE_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_tusize_0082_0.md) value that indicates the requested maximum luma transform block size. This value must by consistent with the pixel size the coded by the user in *SPS.log2_diff_max_min_luma_transform_block_size*. The variable *MaxTbLog2SizeY* is set equal to *log2_min_luma_transform_block_size_minus2 plus 2 plus log2_diff_max_min_luma_transform_block_size*.

### -field max_transform_hierarchy_depth_inter

The maximum hierarchy depth for transform units of coding units coded in inter prediction mode. This value is in the range of zero to *CtbLog2SizeY minus MinTbLog2SizeY*, inclusive.

### -field max_transform_hierarchy_depth_intra

The maximum hierarchy depth for transform units of coding units coded in intra prediction mode. This value is in the range of zero to *CtbLog2SizeY minus MinTbLog2SizeY*, inclusive.

## -remarks

Use [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_hevc_0083_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_hevc_0083_0.md)
