---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_SEQUENCE_STRUCTURE_0095** structure is a hint to the driver of the GOP (group of pictures) being used for rate control purposes only for AV1 video encoding.

## -struct-fields

### -field IntraDistance

Indicates the distance between intra-only frames (or key frames) in the video sequence, or the number of pictures on a sequence of inter-frame pictures. If set to 0, only the first frame will be an key-frame.

### -field InterFramePeriod

Indicates the period for inter-frames to be inserted within the inter frame structure. Note that if **IntraDistance** is set to 0 for infinite inter frame structure, this value must be greater than zero.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_gop_structure_0082_0.md)
