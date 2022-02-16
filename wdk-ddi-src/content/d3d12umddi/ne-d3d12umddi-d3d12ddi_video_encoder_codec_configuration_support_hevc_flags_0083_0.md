---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0083_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0083_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0083_0 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0083_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0083_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0083_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0083_0** enumeration specifies configuration support flags for HEVC encoding.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_NONE

No flags.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_BFRAME_LTR_COMBINED_SUPPORT

Indicates support for use of B frames and long term references frames simultaneously.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_INTRA_SLICE_CONSTRAINED_ENCODING_SUPPORT

Indicates support for slice-constrained encoding, in which every slice in a frame is encoded independently from other slices in the same frame. This mode restricts the motion vector search range to the region box of the current slice; that is, motion vectors outside the slice boundary cannot be used.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_CONSTRAINED_INTRAPREDICTION_SUPPORT

Indicates support for constrained intra-prediction that, if activated, will force the encoding of each intra-coded block with residual data only from other intra-coded blocks (and not from inter-coded blocks). This flag refers to *constrained_intra_pred_flag* in the picture parameter set (PPS).

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_SAO_FILTER_SUPPORT

Indicates support for sample adaptive offset.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_ASYMETRIC_MOTION_PARTITION_SUPPORT

Indicates support for asymmetric motion partition.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_ASYMETRIC_MOTION_PARTITION_REQUIRED

Indicates that asymmetric motion partition must always be enabled. If this flag is set, D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_ASYMETRIC_MOTION_PARTITION_SUPPORT must also be set.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_TRANSFORM_SKIP_SUPPORT

Indicates support for transform skip.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_DISABLING_LOOP_FILTER_ACROSS_SLICES_SUPPORT

Indicates support for disabling loop filter across slices.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0083_0_P_FRAMES_IMPLEMENTED_AS_LOW_DELAY_B_FRAMES

Indicates that frames being encoded with type [**D3D12DDI_VIDEO_ENCODER_FRAME_TYPE_HEVC_0080_P_FRAME**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_type_hevc_0080.md) will be written as low delay B-frames in the compressed bit stream. If this flag is not set, P frames will be written in the compressed bit stream.

> [!NOTE]
>
> When operating in this mode, it is the caller's responsibility to code the correct frame type in _AUD_NUT_ and other parts of the HEVC bit stream, taking into account that P frames will be treated as generalized B frames with only references to past frames in picture order count (POC) order.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_0083_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_hevc_0083_0.md)
