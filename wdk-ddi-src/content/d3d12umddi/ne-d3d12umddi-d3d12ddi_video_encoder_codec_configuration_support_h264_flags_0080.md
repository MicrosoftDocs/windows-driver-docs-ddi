---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080
ms.date: 05/20/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080
---

# D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080** enumeration reports the hardware capabilities for H.264 encoding.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_NONE

Indicates no flags.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_CABAC_ENCODING_SUPPORT

Indicates whether support is available for context-adaptive binary arithmetic coding (CABAC) Encoding.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_INTRA_SLICE_CONSTRAINED_ENCODING_SUPPORT

Indicates whether support is available for slice constrained encoding, in which every slice in a frame is encoded independently from other slices in the same frame. This mode restricts the motion vector search range to the region box of the current slice; that is, motion vectors cannot be used outside the slice boundary.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_BFRAME_LTR_COMBINED_SUPPORT

Indicates whether support is available for using B-frames and long-term references at the same time.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_ADAPTIVE_8x8_TRANSFORM_ENCODING_SUPPORT

Indicates whether support is available for using adaptive 8x8 transforms when encoding.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_DIRECT_SPATIAL_ENCODING_SUPPORT

Indicates support for spatial direct mode.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_DIRECT_TEMPORAL_ENCODING_SUPPORT

Indicates support for temporal direct mode.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_CONSTRAINED_INTRAPREDICTION_SUPPORT

Indicates whether support is available for constrained intra-prediction. When constrained intra-prediction is activated, it forces the encoding of each intra-coded block with residual data only from other intra-coded blocks (and not from inter-coded blocks). This flag refers to *constrained_intra_pred_flag* in the picture parameter set (PPS).

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0099_0_NUM_REF_IDX_ACTIVE_OVERRIDE_FLAG_SLICE_SUPPORT

Indicates that the encoder supports overriding the number of active reference indices at the slice level. This allows for more fine-grained control of reference frames used for prediction on a per-slice basis. Added in Windows 11, version 24H2 (WDDM 3.2).

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_0082_0.md)
