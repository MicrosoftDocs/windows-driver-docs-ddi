---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080** enumeration lists possible H.264 encoder frame types.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080_I_FRAME

An I-frame: completely intra-coded frame.

### -field D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080_P_FRAME

A P-frame (predicted frame): allows references to past frames.

### -field D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080_B_FRAME

A B-frame (bi-directional frame): allows references to both past and future frames, in display order.

### -field D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_H264_0080_IDR_FRAME

An IDR frame (instantaneous decoder refresh frame): A special type of I-frame where no frame after it can reference any frame before it.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_0082_0.md)

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_h264_0082_0.md)
