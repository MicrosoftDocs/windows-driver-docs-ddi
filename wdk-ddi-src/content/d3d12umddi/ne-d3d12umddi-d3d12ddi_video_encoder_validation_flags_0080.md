---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080 enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
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
 - D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0080** enumeration indicates which [**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md) input configuration requests are *not* supported. Use [**D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_validation_flags_0082_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_NONE

No flags (all configuration requests are supported).

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_CODEC_NOT_SUPPORTED

The requested codec is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_PROFILE_NOT_SUPPORTED

The requested profile is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_LEVEL_NOT_SUPPORTED

The requested level is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_INPUT_FORMAT_NOT_SUPPORTED

The requested input format is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_CODEC_CONFIGURATION_NOT_SUPPORTED

The requested codec configuration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_RATE_CONTROL_MODE_NOT_SUPPORTED

The requested rate control mode is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_RATE_CONTROL_CONFIGURATION_NOT_SUPPORTED

The requested rate control configuration is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_INTRA_REFRESH_MODE_NOT_SUPPORTED

The requested intra refresh mode is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_SUBREGION_LAYOUT_MODE_NOT_SUPPORTED

The requested subregion layout mode is not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_RESOLUTION_NOT_SUPPORTED_IN_LIST

One of more of the requested resolutions in the list are not supported.

### -field D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAG_0080_SUGGESTED_TARGET_PROFILE_OR_LEVEL_MISMATCH

The suggested profile or level doesn't match.

## -remarks

Use [**D3D12DDI_VIDEO_ENCODER_VALIDATION_FLAGS_0082_0**](ne-d3d12umddi-d3d12ddi_video_encoder_validation_flags_0082_0.md) for full video encoding feature support for Windows 11 (WDDM 3.0).
