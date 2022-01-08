---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2
ms.date: 02/02/2022
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2
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
req.typenames: D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2
dev_langs:
 - c++
---

## -description

**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2** is a generic structure for codec profiles.

## -struct-fields

### -field DataSize

The size of the referenced data, in bytes.

### -field pH264Profile

Pointer to a [**D3D12DDI_VIDEO_ENCODER_PROFILE_H264_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_profile_h264_0080.md
) value that indicates an H.264 profile.

### -field pHEVCProfile

Pointer to a [**D3D12DDI_VIDEO_ENCODER_PROFILE_HEVC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_profile_hevc_0080.md
) value that indicates an HEVC profile.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information, including an explanation about the pointers to enum types.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_0082_0.md)
