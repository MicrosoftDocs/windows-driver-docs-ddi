---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODE_REFERENCE_FRAMES_0080** structure encapsulates the reconstructed reference images for the encoding operation.

## -struct-fields

### -field NumTexture2Ds

Number of textures in the array.

### -field hDrvTexture2Ds

Pointer to the array of textures.

### -field pSubresources

Pointer to an array of sub-resource indices for the reference textures in **hDrvTexture2Ds**. A value of NULL indicates that sub-resource 0 should be assumed for each resource. With texture arrays within a single resource, the sub-resource indices point to the array index of the first resource plane. With an array of textures in individual resources, the sub-resource index is typically zero.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md)
