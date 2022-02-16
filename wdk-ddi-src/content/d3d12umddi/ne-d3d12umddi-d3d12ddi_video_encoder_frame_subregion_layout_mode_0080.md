---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080** enumeration lists the possible frame subregion encoding modes.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_FULL_FRAME

Full frame output support.

### -field D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_BYTES_PER_SUBREGION

Indicates support for frame subregions to be set as a number of bytes per subregion.

### -field D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_SQUARE_UNITS_PER_SUBREGION_ROW_UNALIGNED

Indicates support for frame subregions to be set as a number of squared blocks per subregion. The number of squared blocks does not need to be a multiple of a row size in squared blocks; that is, the subregions do not need to be row-aligned. Use **D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_UNIFORM_PARTITIONING_ROWS_PER_SUBREGION** or **D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_UNIFORM_PARTITIONING_SUBREGIONS_PER_FRAME** if you need to set a row-aligned number of squared blocks.

### -field D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_UNIFORM_PARTITIONING_ROWS_PER_SUBREGION

Divides the frame into a number of slices, determined by the number of rows per slice. The size of the row, in pixels, can be calculated using the current resolution and [**SubregionBlockPixelsSize**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md) for the current frame resolution.

### -field D3D12DDI_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_0080_UNIFORM_PARTITIONING_SUBREGIONS_PER_FRAME

Specifies the number of slices to divide the frame into.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_resolution_support_limits_0080_2.md)

[**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md)
