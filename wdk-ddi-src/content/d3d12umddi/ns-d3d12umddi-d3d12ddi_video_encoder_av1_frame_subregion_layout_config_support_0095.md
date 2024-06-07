---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095
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
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095** structure describes the AV1 frame subregion layout configuration support settings for the AV1 encoder.

## -struct-fields

### -field Use128SuperBlocks

Input parameter. Boolean that indicates whether the encoder uses 128x128 superblocks. Otherwise the superblock default size 64x64 must be used.

### -field TilesConfiguration

Input parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_TILES_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_subregions_layout_data_tiles_0095.md) structure that specifies the tile configuration to check for support for.

### -field ValidationFlags

Input parameter. A [**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_SUBREGION_LAYOUT_CONFIG_VALIDATION_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_subregion_layout_config_validation_0095_flags.md) enumeration that specifies the flags for the AV1 frame subregion layout configuration validation. Indicates more details when [**D3D12DDI_FEATURE_DATA_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_feature_data_video_encoder_frame_subregion_layout_config_0095.md)**.IsSupported** is false.

### -field MinTileRows

Output parameter. Minimum number of horizontal partitions.

### -field MaxTileRows

Output parameter. Maximum number of horizontal partitions.

### -field MinTileCols

Output parameter. Minimum number of vertical partitions.

### -field MaxTileCols

Output parameter. Maximum number of vertical partitions.

### -field MinTileWidth

Output parameter. Minimum width of any tile, in superblock units.

### -field MaxTileWidth

Output parameter. Maximum width of any tile, in superblock units.

### -field MinTileArea

Output parameter. Minimum dimension of any tile, in superblock units.

### -field MaxTileArea

Output parameter. Maximum dimension of any tile, in superblock units.

### -field TileSizeBytesMinus1

Output parameter. Specifies the number of bytes needed to code each tile size. Related to the driver writing the [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_METADATA_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_metadata_0083_0.md)**.bSize** elements in the resolved metadata. The API Client will write tile_size_bytes_minus_1 = (TileSizeBytesMinus1) in frame_header_obu/uncompressed_header/tile_info when writing the frame header OBU, and when writing le(TileSizeBytes) tile_size_minus_1 in tile_group_obu().

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_config_support_0095.md)
