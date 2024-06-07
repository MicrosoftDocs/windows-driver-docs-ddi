---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095
---

## -description

The **D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095** enumeration defines the compound prediction types for an AV1 encoder.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095_SINGLE_REFERENCE:0

Indicates that all inter blocks will use single prediction. Thie value is equivalent to AV1 syntax reference_select equal to 0.

### -field D3D12DDI_VIDEO_ENCODER_AV1_COMP_PREDICTION_TYPE_0095_COMPOUND_REFERENCE:1

Indicates that the mode info for inter blocks contains the syntax element comp_mode that indicates whether to use single or compound reference prediction. This value is equivalent to AV1 syntax reference_select equal to 1.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_CODEC_AV1_PICTURE_CONTROL_SUPPORT_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_av1_picture_control_support_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_picture_control_codec_data_0095.md)

[**D3D12DDI_VIDEO_ENCODER_AV1_POST_ENCODE_VALUES_0095**](ns-d3d12umddi-d3d12ddi_video_encoder_av1_post_encode_values_0095.md)
