---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095** structure describes the picture control support settings for the AV1 encoder.

## -struct-fields

### -field PredictionMode

Input parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_comp_prediction_type_0095.md) enumeration that specifies the requested prediction mode to be used. The driver must return the output parameters assuming a frame will be encoded using this prediction mode in the picture params structure.

### -field MaxUniqueReferencesPerFrame

Output parameter. Indicates how many unique reference frames in the DPB can be selected at the same time for a given frame from any of the reference types (LAST, ..., ALTREF, etc) in the picture control parameters from the DPB that the API Client manages. In other words, the maximum number distinct (and with **ReconstructedPictureResourceIndex** != 0xFF) entries in [**D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080**](ns-d3d12umddi-d3d12ddi_video_encode_reference_frames_0080.md)**.pSubresources**[ReferenceFramesReconPictureDescriptors[ReferenceIndices[i]].ReconstructedPictureResourceIndex] for i in [0..7].

### -field SupportedFrameTypes

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095_flags.md) enumeration that specifies the supported frame types to be used in [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095.md).

### -field SupportedReferenceWarpedMotionFlags

Output parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_WARPED_MOTION_TRANSFORMATION_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_reference_warped_motion_transformation_0095_flags.md) enumeration that specifies the supported types to be used in  [**D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_WARPED_MOTION_INFO_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_reference_picture_warped_motion_info_0095.md)**.TransformationType**.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_picture_control_support_0080_2.md)
