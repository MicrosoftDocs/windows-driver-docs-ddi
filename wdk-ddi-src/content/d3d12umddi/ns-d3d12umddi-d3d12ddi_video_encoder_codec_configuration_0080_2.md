---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2** structure contains configuration information for a video codec. Use [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0082_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pH264Config

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_h264_0080_2.md) structure that contains H.264 codec configuration information.

### -field pHEVCConfig

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_0080_2.md) structure that contains HEVC codec configuration information.

## -remarks

Use [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0082_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).
