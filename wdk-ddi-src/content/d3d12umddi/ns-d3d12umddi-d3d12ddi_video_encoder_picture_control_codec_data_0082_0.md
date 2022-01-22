---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_0082_0** structure contains picture control codec-specific data.

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pH264PicData

Pointer to a [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_h264_0082_0.md) structure containing the picture-level control data for H.264 encoding.

### -field pHEVCPicData

Pointer to a [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_hevc_0082_0.md) structure containing the picture-level control data for HEVC encoding.

## -remarks

Slice-level picture reference lists reordering is not supported.

Weighted inter-prediction is not supported.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md)
