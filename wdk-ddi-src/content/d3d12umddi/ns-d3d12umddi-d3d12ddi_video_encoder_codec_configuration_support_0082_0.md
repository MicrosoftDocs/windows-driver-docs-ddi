---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0082_0** structure is used to represent a codec-specific configuration for video encoding.

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pH264Support

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_0082_0.md) structure that contains configuration support parameters for H.264 encoding.

### -field pHEVCSupport

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_hevc_0082_0.md) structure that contains configuration support parameters for HEVC encoding.

## -remarks

Use [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_0083_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_0083_0.md)
