---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095
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
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MAP_0095** structure contains segmentation map information for an AV1 frame.

## -struct-fields

### -field SegmentsMapByteSize

Size in bytes of the **pSegmentsMap** buffer.

### -field pSegmentsMap

In raster order, contains the AV1 syntax segment_id between [0..7] for each block in the frame. The block size is **SegmentationBlockSize** as reported by the driver in [**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md).

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)
