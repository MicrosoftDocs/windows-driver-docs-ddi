---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095
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
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095** structure contains configuration information for segmentation for an AV1 frame.

## -struct-fields

### -field UpdateMap

A flag indicating whether the segmentation map should be updated for the current frame. If set, the encoder will use the new segmentation map provided in the [**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_map_0095.md) structure.

### -field TemporalUpdate

A flag indicating whether the segmentation map is updated based on temporal information. If set, segments may be predicted from previous frames.

### -field UpdateData

A flag indicating whether the data for the segments should be updated. If set, the encoder will use the new data provided in the **SegmentsData** array.

### -field NumSegments

When using [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_0095_FLAG_ENABLE_FRAME_SEGMENTATION_AUTO**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_0095_flags.md) and the driver writes it back on post encode values, a value of **NumSegments** = 0 indicated that segmentation_enabled must be 0 in the frame header. Otherwise, the API client codes segmentation_params() in the frame header accordingly with the other parameters in this structure.

When using [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_0095_FLAG_ENABLE_FRAME_SEGMENTATION_CUSTOM**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_0095_flags.md), indicates the input number of segments.

### -field SegmentsData[8]

Array of [**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENT_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segment_data_0095.md) structures that contain the data for each segment. The number of elements in the array is specified by **NumSegments**.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095.md)
