---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS** enumeration specifies the flags for the AV1 frame subregion layout configuration validation.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_NONE:0x0

No flags are specified.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_NOT_SPECIFIED:0x1

When this flag is set, indicates that the requested tiles configuration is not supported due to a reason not specified by any of the other flag categories.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_CODEC_CONSTRAINT:0x2

When this flag is set, indicates that the requested tiles configuration is not supported due to codec constraints. An example on this for AV1 would be [**D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_feature_data_video_encoder_frame_subregion_layout_config_0095.md)**.Level**.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_HARDWARE_CONSTRAINT:0x4

When this flag is set, indicates that the requested tiles configuration is not supported due to hardware constraints.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_ROWS_COUNT:0x8

When this flag is set, indicates that the number of tile rows requested is not supported.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_COLS_COUNT:0x10

When this flag is set, indicates that the number of tile columns requested is not supported.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_WIDTH:0x20

When this flag is set, indicates that one or more tiles widths in the requested configuration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_AREA:0x40

When this flag is set, indicates that one or more tiles areas in the requested configuration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAG_TOTAL_TILES:0x80

When this flag is set, indicates that the total number of tiles in the requested partition exceeds the total supported tiles count. Please see [**D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md)**.MaxSubregionsNumber**.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_frame_subregion_layout_config_support_0095.md)
