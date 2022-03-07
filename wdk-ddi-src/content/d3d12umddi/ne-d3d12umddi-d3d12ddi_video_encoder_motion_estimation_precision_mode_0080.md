---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080** enumeration lists the possible motion estimation precision modes.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080_MAXIMUM

Indicates no limit in the precision for motion estimation vectors, thus allowing the maximum precision supported by the driver.

### -field D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080_FULL_PIXEL

Indicates that the precision for motion estimation vectors has to be at most full-pixel.

### -field D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080_HALF_PIXEL

Indicates that the precision for motion estimation vectors has to be at most half-pixel.

### -field D3D12DDI_VIDEO_ENCODER_MOTION_ESTIMATION_PRECISION_MODE_0080_QUARTER_PIXEL

Indicates that the precision for motion estimation vectors has to be at most quarter-pixel.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_ENCODER_0082_0**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_0082_0.md)
