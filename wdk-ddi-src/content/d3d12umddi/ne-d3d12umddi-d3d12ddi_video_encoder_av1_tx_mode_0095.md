---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095** enumeration defines the list of distinct transform modes that can be used in AV1 video encoding.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095_ONLY4x4:0

Indicates that only 4x4 transform blocks can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095_LARGEST:1

Indicates that the largest transform block size can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095_SELECT:2

Indicates that the driver can dynamically select the transform size for each block.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_TX_MODE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_tx_mode_0095_flags.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md)
