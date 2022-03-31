---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2** structure represents picture control support for multiple codecs.

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pH264Support

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_picture_control_support_h264_0080_2.md) structure that contains picture control support parameters for H.264 encoding.

### -field pHEVCSupport

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_HEVC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_picture_control_support_hevc_0080_2.md) structure that contains picture control support parameters for HEVC encoding.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDICAPS_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_DATA_0080_2**](ns-d3d12umddi-d3d12ddicaps_video_encoder_codec_picture_control_support_data_0080_2.md)
