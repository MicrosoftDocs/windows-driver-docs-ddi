---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2** structure contains configuration information for an HEVC (H.265) codec. Use [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_0082_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).

## -struct-fields

### -field ConfigurationFlags

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_flags_0080.md) value that defines the set of enabled features. Flags can be combined.

### -field MinLumaCodingUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_CUSIZE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_cusize_0080.md) value that indicates the minimum luma coding block size to be used in the encoder. This value matches the value coded by the user in the Sequence Parameter Set (SPS).

### -field MaxLumaCodingUnitSize

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_CUSIZE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_cusize_0080.md) value that indicates the maximum luma coding block size to be used in the encoder. This value matches the value that coded by the user in the SPS.

## -remarks

Use [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_0082_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).
