---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095** enumeration defines the list of distinct restoration filter types that can be used in the AV1 video encoding process, where each value represents a specific restoration filter.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095_DISABLED:0

Indicates that no restoration filter is to be applied.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095_SWITCHABLE:1

Indicates that the encoder can choose between the Wiener and Sgrproj restoration filters.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095_WIENER:2

Indicates that the Wiener restoration filter should be applied.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_TYPE_0095_SGRPROJ:3

Indicates that the Self-Guided Restoration (Sgrproj) restoration filter should be applied.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_restoration_config_0095.md)  

[**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)  
