---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAGS** enumeration is a bitwise OR of values that define the loop restoration tile sizes that the encoder supports.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAG_NOT_SUPPORTED:0

Indicates that the encoder does not support loop restoration.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAG_32x32:0x1

Indicates that the encoder supports a 32x32 loop restoration tile size.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAG_64x64:0x2

Indicates that the encoder supports a 64x64 loop restoration tile size.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAG_128x128:0x4

Indicates that the encoder supports a 128x128 loop restoration tile size.

### -field D3D12DDI_VIDEO_ENCODER_AV1_RESTORATION_SUPPORT_0095_FLAG_256x256:0x8

Indicates that the encoder supports a 256x256 loop restoration tile size.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md)
