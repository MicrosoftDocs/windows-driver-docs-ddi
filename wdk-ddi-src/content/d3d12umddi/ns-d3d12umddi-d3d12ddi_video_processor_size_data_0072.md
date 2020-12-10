---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
title: D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
tech.root: display
description: Retrieves the memory allocation size of a video processor created with the given properties.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
f1_keywords:
 - D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
 - d3d12umddi/D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
dev_langs:
 - c++
---

## -description

Retrieves the memory allocation size of a video processor created with the given properties.

## -struct-fields

### -field VideoProcessorDesc

[in] A [**D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043**](ns-d3d12umddi-d3d12ddi_video_processor_size_data_0043.md) structure.

### -field Protected

[in] If TRUE, the video processor is created with a protected resource session and used with protected resources.

### -field MemoryPoolL0Size

[out] The L0 size of the heap object. Memory Pool L0 is the memory pool “closest” to the GPU.  In the case of UMA adapters, this is the amount of system memory used.  For discrete adapters, this is the amount of discrete memory used.

### -field MemoryPoolL1Size

[out] The L1 size of the heap object.  Memory Pool L1 is the memory pool “second closest” to the GPU.  In the case of UMA adapters, this value is zero.  In the case of discrete adapters, this is the amount of system memory used.

## -remarks

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043**](ns-d3d12umddi-d3d12ddi_video_processor_size_data_0043.md)

