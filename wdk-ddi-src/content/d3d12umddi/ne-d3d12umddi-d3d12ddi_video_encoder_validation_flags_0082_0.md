---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0** enumeration indicates which [**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md) input configuration requests are *not* supported.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_NONE

No flags (all configuration requests are supported).

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_CODEC_NOT_SUPPORTED

The requested codec is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_INPUT_FORMAT_NOT_SUPPORTED

The requested input format is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_CODEC_CONFIGURATION_NOT_SUPPORTED

The requested codec configuration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_RATE_CONTROL_MODE_NOT_SUPPORTED

The requested rate control mode is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_RATE_CONTROL_CONFIGURATION_NOT_SUPPORTED

The requested rate control configuration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_INTRA_REFRESH_MODE_NOT_SUPPORTED

The requested intra refresh mode is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_SUBREGION_LAYOUT_MODE_NOT_SUPPORTED

The requested subregion layout mode is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_RESOLUTION_NOT_SUPPORTED_IN_LIST

One of more of the requested resolutions in the list are not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0082_0_GOP_STRUCTURE_NOT_SUPPORTED

The requested group of pictures (GOP) structure is not supported.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)

[**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md)
