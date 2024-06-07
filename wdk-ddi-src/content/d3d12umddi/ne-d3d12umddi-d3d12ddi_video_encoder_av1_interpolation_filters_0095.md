---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095
ms.date: 05/14/2024
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095
---

## -description

The **D3D12_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS** enumeration defines the list of distinct interpolation filter types that can be used in the AV1 video encoding process, where each value represents a specific interpolation filter.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095_EIGHTTAP:0

The eight-tap interpolation filter uses eight samples to create a prediction.

### -field D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095_EIGHTTAP_SMOOTH:1

The eight-tap smooth interpolation filter is a variant of the eight-tap filter that applies a smoothing function to reduce sharpness.

### -field D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095_EIGHTTAP_SHARP:2

The eight-tap sharp interpolation filter is another variant of the eight-tap filter that emphasizes sharpness.

### -field D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095_BILINEAR:3

The bilinear interpolation filter uses two samples to create a prediction.

### -field D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095_SWITCHABLE:4

The encoder has the capability to dynamically switch between different interpolation filters based on the content of each block. Instead of using a single filter for the entire video frame, the encoder can choose the most appropriate filter for each block to optimize quality and compression efficiency.

## -remarks

See [D3D12 AV1 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12-av1) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_AV1_INTERPOLATION_FILTERS_0095_FLAGS**](ne-d3d12umddi-d3d12ddi_video_encoder_av1_interpolation_filters_0095_flags.md)
