---
UID: NS:d3d12umddi.D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060
title: D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060
author: windows-driver-content
description: Describes the output of the resolve operation.
tech.root: display
ms.assetid: 6e40d600-52b8-41be-929c-bf02163dac98
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060"
 - "D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060, D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDI_RESOLVE_VIDEO_MOTION_VECTOR_HEAP_OUTPUT_0060 structure

## -description

Describes the output of the resolve operation.

## -struct-fields

### -field hDrvMotionVectorTexture2D

The output resource for resolved motion vectors. Motion vectors are resolved to a DXGI_FORMAT_R16G16_SINT 2D texture. The resolved data is expected to be a signed 16-byte integer with quarter pel unit,s with the X vector component stored in the R component and the Y vector component stored in the G component. Motion vectors are stored in a 2D layout that corresponds to the pixel layout of the original input textures.

### -field MotionVectorCoordinate

Specifies the output origin of the motion vectors. The remaining sub-region must be large enough to store all motion vectors per block specified by the input PixelWidth/PixelHeight and the [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SEARCH_BLOCK_SIZE_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_search_block_size_0053.md).

## -remarks

## -see-also
