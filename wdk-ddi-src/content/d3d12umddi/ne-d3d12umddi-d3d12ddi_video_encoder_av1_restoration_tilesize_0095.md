---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095** corresponds to the size of loop restoration units, in units of samples in the current plane.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095_DISABLED:0

Indicates that no loop restoration is to be applied.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095_32x32:1

Indicates that the loop restoration tile size is 32x32.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095_64x64:2

Indicates that the loop restoration tile size is 64x64.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095_128x128:3

Indicates that the loop restoration tile size is 128x128.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TILESIZE_0095_256x256:4

Indicates that the loop restoration tile size is 256x256.

## -remarks

The enum values are based on lr_unit_shift and lr_uv_shift in lr_params() AV1 syntax and the RESTORATION_TILESIZE_MAX(256) AV1 spec constant.

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_restoration_config_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_restoration_type_0095.md)
