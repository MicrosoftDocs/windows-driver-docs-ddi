---
UID: NS:d3d12umddi.D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053
title: D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053 (d3d12umddi.h)
description: Describes the output of the resolve operation.
ms.assetid: e77a7822-256f-42c8-b812-e99bc274a732
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053"
ms.keywords: D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053, D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
dev_langs:
 - c++
---

# D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0053 structure

## -description

Describes the output of the resolve operation.

## -struct-fields

### -field hDrvMotionVectorTexture2D

The output resource for resolved motion vectors. Motion vectors are resolved to a DXGI_FORMAT_R16G16_SINT 2d texture. The resolved data is expected to be a signed 16-byte integer with quarter pel unit,s with the X vector component stored in the R component and the Y vector component stored in the G component. Motion vectors are stored in a 2D layout that corresponds to the pixel layout of the original input textures.

### -field MotionVectorCoordinate

Specifies the output origin of the motion vectors. The remaining sub-region must be large enough to store all motion vectors per block specified by the input PixelWidth/PixelHeight and the [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SEARCH_BLOCK_SIZE_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_search_block_size_0053.md).

### -field hDrvDifferencesMetricTexture2D

When the [D3D12DDI_VIDEO_MOTION_ESTIMATOR_DIFFERENCES_METRIC_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_differences_metric_0053.md) is *D3D12DDI_VIDEO_MOTION_ESTIMATOR_DIFFERENCES_METRIC_0053_NONE*, this parameter must be nullptr.

When the D3D12DDI_VIDEO_MOTION_ESTIMATOR_DIFFERENCES_METRIC_0053 is *D3D12DDI_VIDEO_MOTION_ESTIMATOR_DIFFERENCES_METRIC_0053_SUM_OF_ABSOLUTE_TRANSFORMED_DIFFERENCES*, this is a DXGI_FORMAT_R32_UNORM or DXGI_FORMAT_R32_UINT texture 2D. The values are stored in a 2D layout that corresponds to the pixel layout of the original input textures.

### -field DifferencesMetricCoordinate
 
Specifies the output origin of the differences metric. The remaining sub-region must be large enough to store a difference metric per block specified by the input PixelWidth/PixelHeight of the [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SEARCH_BLOCK_SIZE_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_search_block_size_0053.md).

## -remarks

## -see-also
