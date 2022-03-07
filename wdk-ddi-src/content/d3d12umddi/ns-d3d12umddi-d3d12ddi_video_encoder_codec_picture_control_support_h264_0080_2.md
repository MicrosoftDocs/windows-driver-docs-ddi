---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264_0080_2** structure represents picture control support settings for H.264 encoding.

## -struct-fields

### -field MaxL0ReferencesForP

The maximum value allowed in the slice headers for ```(num_ref_idx_l0_active_minus1 plus 1)``` when encoding P frames. This is equivalent to the maximum size of an L0 for a P frame supported.

### -field MaxL0ReferencesForB

The maximum value allowed in the slice headers for ```(num_ref_idx_l0_active_minus1 plus 1)``` when encoding B frames. This is equivalent to the maximum size of an L0 for a B frame supported.

### -field MaxL1ReferencesForB

The maximum value allowed in the slice headers for ```(num_ref_idx_l1_active_minus1 plus 1)``` when encoding B frames. This is equivalent to the maximum size of an L1 for a B frame supported.

### -field MaxLongTermReferences

The maximum number of references used in a frame that can be marked as long term reference.

### -field MaxDPBCapacity

The maximum number of unique pictures that can be used from the decoded picture buffer (DPB) that the caller manages (number of unique indices in L0 union L1) for a given [**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) command on the hardware.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_picture_control_support_0080_2.md)
