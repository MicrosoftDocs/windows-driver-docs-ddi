---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAGS** enumeration defines the supported segmentation modes that can be used for the segmentation map in the AV1 video encoding process.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_NONE

Indicates that no segmentation flags are set.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_DISABLED

Indicates that the use of segmentation is disabled.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_ALT_Q

Indicates that alternative quantization parameters within segments can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_ALT_LF_Y_V

Indicates that alternative vertical loop filter strengths for the luma (Y) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_ALT_LF_Y_H

Indicates that alternative horizontal loop filter strengths for the luma (Y) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_ALT_LF_U

Indicates that alternative loop filter strengths for the chroma (U) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_ALT_LF_V

Indicates that alternative loop filter strengths for the chroma (V) component can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_REF_FRAME

Indicates that alternative reference frames can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_ALT_SKIP

Indicates that alternative skip flags can be used.

### -field D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095_FLAG_ALT_GLOBALMV

Indicates that alternative global motion vector parameters can be used.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_CONFIG_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_config_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_SEGMENTATION_MODE_0095**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_segmentation_mode_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_codec_configuration_support_0095.md)  
