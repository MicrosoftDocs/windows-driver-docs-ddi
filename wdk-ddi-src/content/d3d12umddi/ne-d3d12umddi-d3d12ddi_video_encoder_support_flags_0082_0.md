---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0082_0 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0082_0** enumeration reports the support for a given configuration. Use [**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md) for windows 11 (WDDM 3.0).

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_NONE

No flags are set (indicates no support).

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_GENERAL_SUPPORT_OK

Indicates whether the given configuration is generally supported by the encoder, in combination with the remaining flags to convey certain limitations or no general support. The D3D12 Debug layer can provide further information.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RATE_CONTROL_RECONFIGURATION_AVAILABLE

Indicates support for changing the rate control in the middle of the encoding session.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RESOLUTION_RECONFIGURATION_AVAILABLE

Indicates support for changing the resolution in the middle of the encoding session.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RATE_CONTROL_VBV_SIZE_CONFIG_AVAILABLE

When set, enables configuring the video buffering verifier (VBV) initial fullness and capacity for rate control algorithms.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RATE_CONTROL_FRAME_ANALYSIS_AVAILABLE

Indicates support for rate control modes that involve frame analysis to optimize the bitrate usage at the cost of slower performance.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RECONSTRUCTED_FRAMES_REQUIRE_CONTIGUOUS_TEXTURE_ARRAYS

When set, textures that refer reconstructed pictures can only be referenced as a texture array, as opposed to an array of separate texture 2D resources with each resource having array size of 1.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RATE_CONTROL_DELTA_QP_AVAILABLE

Indicates support for delta quantization parameter (QP) usage in rate control.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_SUBREGION_LAYOUT_RECONFIGURATION_AVAILABLE

Indicates support for dynamic subregion layout changes during an encoding session.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RATE_CONTROL_ADJUSTABLE_QP_RANGE_AVAILABLE

Indicates support for adjustable QP range in rate control.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RATE_CONTROL_INITIAL_QP_AVAILABLE

Indicates support for adjustable initial QP in rate control.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_RATE_CONTROL_MAX_FRAME_SIZE_AVAILABLE

Indicates support for setting a maximum cap in the bitrate algorithm per each encoded frame.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0082_0_SEQUENCE_GOP_RECONFIGURATION_AVAILABLE

Indicates support for dynamic group of pictures (GOP) changes during an encoding session.

## -remarks

Use [**D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0**](ne-d3d12umddi-d3d12ddi_video_encoder_support_flags_0083_0.md) for windows 11 (WDDM 3.0).
