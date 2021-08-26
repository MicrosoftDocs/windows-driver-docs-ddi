---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2
ms.date: 08/31/2021 
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2
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
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0080_2
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2** structure configures the sequence level parameters for an H.264 encoder.

## -struct-fields

### -field ConfigurationFlags

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_h264_flags_0080.md) value that defines the set of enabled features for an H.264 encoder. Flags can be combined.

### -field DirectModeConfig

A [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_DIRECT_MODES_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_h264_direct_modes_0080.md) value that specifies configuration information related to DIRECT modes.

### -field pic_order_cnt_type

The picture order count type filter mode as defined in the H.264 standard under *pic_order_cnt_type* in the sequence parameter set. The value of **pic_order_cnt_type** is in the range of 0 to 2, inclusive.

### -field log2_max_frame_num_minus4

The value of the variable *MaxFrameNum* that is used in *frame_num* related derivations as follows: ``` MaxFrameNum = 2^(log2_max_frame_num_minus4 + 4) ```.

The value of **log2_max_frame_num_minus4** is in the range of 0 to 12, inclusive.

### -field log2_max_pic_order_cnt_lsb_minus4

The value of the variable *MaxPicOrderCntLsb* that is used in the decoding process for picture order count as specified in the H.264 specification as follows: ``` MaxPicOrderCntLsb = 2^ (log2_max_pic_order_cnt_lsb_minus4 + 4)```.

The value of **log2_max_pic_order_cnt_lsb_minus4** is in the range of 0 to 12, inclusive.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_0080_2.md)
