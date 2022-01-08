---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0082_0
ms.date: 02/02/2022
targetos: Windows
description: 
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
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAGS_0082_0** enumerator lists the possible set of enabled features for an HEVC (H.265) codec.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_NONE

No flags are specified.

### -field  the use of the intra constrained slices flag in picture control. This mode restricts the motion vector search range to the region box of the current slice (for example, motion vectors outside the slice boundary cannot be used).

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_ENABLE_SAO_FILTER

If set, enables the sample adaptive offset filter.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_DISABLE_LOOP_FILTER_ACROSS_SLICES

If set, disable the loop filtering across slices.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_ALLOW_REQUEST_INTRA_CONSTRAINED_SLICES

If set, allowsD3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_ENABLE_LONG_TERM_REFERENCES

If set, enables the use of long-term references in the picture reference management structures for HEVC.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_USE_ASYMETRIC_MOTION_PARTITION

If set, enables asymmetric motion partitioning. NOTE: If [**VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAG_0082_0_ASYMETRIC_MOTION_PARTITION_REQUIRED**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_hevc_flags_0082_0.md) was reported, this flag must always be enabled.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_ENABLE_TRANSFORM_SKIPPING

If set, enables transform skipping.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_0082_0_USE_CONSTRAINED_INTRAPREDICTION

If set, enables constrained intra prediction. This value refers to *constrained_intra_pred_flag* in the Picture Parameter Set (PPS).

## -remarks

The host (D3D12 lower-level encoding API) sets these configuration flags based on the limits queried at the API level.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_hevc_0082_0.md)

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_HEVC_FLAGS_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0082_0.md)
