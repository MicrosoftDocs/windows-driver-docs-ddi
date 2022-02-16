---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0** structure represents a group of pictures (GOP) definition for a video codec.

## -struct-fields

### -field DataSize

Size of the referenced data, in bytes.

### -field pH264GroupOfPictures

Pointer to a [*D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_gop_structure_h264_0082_0.md) structure representing the GOP structure for H.264 encoding.

### -field pHEVCGroupOfPictures

Pointer to a [*D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_gop_structure_hevc_0082_0.md) structure representing the GOP structure for HEVC encoding.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md)
