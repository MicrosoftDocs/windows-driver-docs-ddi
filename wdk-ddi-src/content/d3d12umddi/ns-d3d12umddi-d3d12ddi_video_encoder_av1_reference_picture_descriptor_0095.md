---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095
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
 - D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_DESCRIPTOR_0095** structure describes a reference picture used in AV1 encoding.

## -struct-fields

### -field ReconstructedPictureResourceIndex

Maps the current reference picture described by this structure to a resource in the [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md)**.ReferenceFrames** array.

If the associated slot in [**ReferenceFramesReconPictureDescriptors**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md) containing this structure has a valid **ReconstructedPictureResourceIndex** reference to the **D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0.ReferenceFrames** array then the allowed range of values is [0..254]. Otherwise, if it corresponds to an empty/unused slot in the decoded picture buffer (DPB), then the value must be set to D3D12_VIDEO_ENCODER_AV1_INVALID_DPB_RESOURCE_INDEX.

### -field TemporalLayerIndexPlus1

The temporal layer index of the reference picture incremented by one of the previously encoded frame now used as reference.

### -field SpatialLayerIndexPlus1

Picture spatial layer index plus one of the previously encoded frame now used as reference.

### -field FrameType

A [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095.md) value that specifies the type of frame used to encode the described reference frame associated to this entry.

### -field WarpedMotionInfo

A [**D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_PICTURE_WARPED_MOTION_INFO_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_reference_picture_warped_motion_info_0095.md) structure that contains the global motion parameters. Only used if supported in [**D3D12DDI_VIDEO_ENCODER_AV1_REFERENCE_WARPED_MOTION_TRANSFORMATION_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_reference_warped_motion_transformation_0095_flags.md).

### -field OrderHint

The reference ref_order_hint AV1 syntax. Even when reference order hints are not coded in the AV1 bitstream, **OrderHint** here must be set to the value used in [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)**.OrderHint** for the previously encoded frame that is now being held as reference by this descriptor. This information hints to the driver, in a frame type that allows frame references, which are from past frames and which are from future frames (in display order) when comparing against the current frame value of **D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095.OrderHint**.

### -field PictureIndex

The unique picture index of the previously encoded frame that is stored in this entry as a reference. This parameter is not related in any way to the AV1 standard syntax, but merely used for API client implementation tracking instead.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)
