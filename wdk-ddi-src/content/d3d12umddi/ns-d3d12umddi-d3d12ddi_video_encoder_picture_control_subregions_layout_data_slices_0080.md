---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080 structure.
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
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLICES_0080** structure defines subregions as slices for codecs that support this partitioning mode.

## -struct-fields

### -field MaxBytesPerSlice

This member is used exclusively with [**VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_BYTES_PER_SUBREGION**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md). **MaxBytesPerSlice** specifies the maximum number of bytes per slice to be used.

### -field NumberOfCodingUnitsPerSlice

This member is used exclusively with [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_SQUARE_UNITS_PER_SUBREGION_ROW_UNALIGNED**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md). **NumberOfCodingUnitsPerSlice** specifies the number of squared blocks to be used per slice. The size in pixels of the squared regions can be calculated using the current resolution and [**SubregionBlockPixelsSize**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md) for the current frame resolution.

### -field NumberOfRowsPerSlice

This member is used exclusively with [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_UNIFORM_PARTITIONING_ROWS_PER_SUBREGION**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md). **NumberofRowsPerSlice** specifies the number of squared blocks rows per slice for the frame to be divided into. The size in pixels of the squared regions can be calculated using the current resolution and [**SubregionBlockPixelsSize**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md) for the current frame resolution.

### -field NumberOfSlicesPerFrame

This member is used exclusively with [**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_UNIFORM_PARTITIONING_SUBREGIONS_PER_FRAME**](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md). **NumberOfSlicesPerFrame** specifies the number of slices to divide the frame into.

## -remarks

For modes that imply a fixed number of slices, the number of slices selected must be less than [**MaxSubregionsNumber**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md) and the selected resolution.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080*](ne-d3d12umddi-d3d12ddi_video_encoder_frame_subregion_layout_mode_0080.md)

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_subregions_layout_data_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md)
