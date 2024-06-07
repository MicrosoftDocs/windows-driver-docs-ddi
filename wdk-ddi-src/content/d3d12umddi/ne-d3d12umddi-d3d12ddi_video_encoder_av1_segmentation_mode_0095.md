---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095** enumeration defines the distinct segmentation modes that can be used for the segmentation map in the AV1 video encoding process.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_DISABLED:0

Indicates that the use of segmentation is disabled.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_Q:1

Indicates that alternative quantization parameters within segments can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_LF_Y_V:2

Indicates that alternative lvertical oop filter strengths for the luma (Y) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_LF_Y_H:3

Indicates that alternative horizontal loop filter strengths for the luma (Y) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_LF_U:4

Indicates that alternative loop filter strengths for the chroma (U) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_LF_V:5

Indicates that alternative loop filter strengths for the chroma (V) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_REF_FRAME:6

Indicates that alternative reference frame selection can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_SKIP:7

Indicates whether certain segments should be skipped (i.e., encoded using inter prediction modes only).

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_ALT_GLOBALMV:8

Indicates that alternative global motion vector parameters can be used.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_config_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_mode_0095_flags.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md)  
