---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAGS** enumeration defines the frame types that an AV1 encoder can support.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAG_NONE

Indicates that the frame type is not specified.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAG_KEY_FRAME

Corresponds to the key frame type.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAG_INTER_FRAME

Corresponds to the inter frame type.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAG_INTRA_ONLY_FRAME

Corresponds to the intra-only frame type.

### -field D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095_FLAG_SWITCH_FRAME

Corresponds to the switch frame type.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_FRAME_TYPE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_frame_type_0095.md)

[**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_picture_control_support_0095.md)
