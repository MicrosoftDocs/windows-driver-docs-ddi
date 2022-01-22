---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2
---

## -description

The **D3D12DDI_VIDEO_ENCODER_LEVEL_SETTING_0080_2** structure encapsulates a generic level-related setting definition.

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pH264LevelSetting

Pointer to a [**D3D12DDI_VIDEO_ENCODER_LEVELS_H264_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_levels_h264_0080.md) value that identifies the H.264 level.

### -field pHEVCLevelSetting

Pointer to a [**D3D12DDI_VIDEO_ENCODER_LEVEL_TIER_CONSTRAINTS_HEVC_0080**](ns-d3d12umddi-d3d12ddi_video_encoder_level_tier_constraints_hevc_0080.md) structure that identifies the level and tier for an HVEC level configuration.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_heap_0080_2.md)
