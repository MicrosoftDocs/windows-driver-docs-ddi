---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080
ms.date: 02/02/2022
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080
dev_langs:
 - c++
---

## -description

**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080** lists the possible configuration information related to DIRECT modes.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080_DISABLED

Disables DIRECT modes.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080_TEMPORAL

Enables DIRECT temporal mode. Check the [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_DIRECT_TEMPORAL_ENCODING_SUPPORT**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0080.md) flag for support.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080_SPATIAL

Enables DIRECT spatial mode. Check the [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_DIRECT_SPATIAL_ENCODING_SUPPORT**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0080.md) flag for support.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_h264_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0080.md)
