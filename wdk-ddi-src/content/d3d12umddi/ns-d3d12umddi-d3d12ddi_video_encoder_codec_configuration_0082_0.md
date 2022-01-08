---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0
ms.date: 02/02/2022
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0082_0** structure contains configuration information for a video codec.

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pH264Config

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_h264_0082_0.md) structure that contains H.264 codec configuration information.

### -field pHEVCConfig

Pointer to a [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_0082_0.md) structure that contains HEVC codec configuration information.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_0082_0.md)

[**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0082_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0082_0.md)
