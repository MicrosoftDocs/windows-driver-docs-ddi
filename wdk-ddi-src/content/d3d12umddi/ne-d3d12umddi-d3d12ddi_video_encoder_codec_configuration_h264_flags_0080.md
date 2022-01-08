---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080
ms.date: 02/02/2022
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080.
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
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAGS_0080** enumerator lists the possible set of enabled features for an H.264 codec.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAG_NONE_0080

No flags are specified.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAG_USE_CONSTRAINED_INTRAPREDICTION_0080

When set, this flag forces the encoding of each intra-coded block with residual data only from other intra-coded blocks in the frame (and not from inter-coded blocks, for example). Check the [**D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_FLAGS_H264_CONSTRAINED_INTRAPREDICTION_SUPPORT**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0080.md) flag for support. This flag refers to *constrained_intra_pred_flag* in the H.264 Picture Parameter Set (PPS).

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAG_USE_ADAPTIVE_8x8_TRANSFORM_0080

When set, this flag enables the usage of adaptive 8x8 transforms. Check the [**D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_FLAGS_H264_ADAPTIVE_8x8_TRANSFORM_ENCODING_SUPPORT**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0080.md) flag for support.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAG_ENABLE_CABAC_ENCODING_0080

When set, this flag enables entropy coding using the context-adaptive binary arithmetic coding (CABAC) algorithm. When this flag is not set, the context-adaptive variable-length coding (CAVLC) algorithm is used. Check the [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAG_0080_CABAC_ENCODING_SUPPORT**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0080.md) flag for CABAC support.

### -field D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_FLAG_ALLOW_REQUEST_INTRA_CONSTRAINED_SLICES_0080

When set, the user can request, for each frame with a special flag in the picture control structure, that slices of such a frame be coded independent of each other. This mode restricts the motion vector search range to the region box of the current slice (for example, motion vectors cannot be used outside of the slice boundary).

## -remarks

Flags can be combined.

The host (D3D12 lower-level encoding API) sets these configuration flags based on the limits queried at the API level.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_h264_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_flags_0080.md)
