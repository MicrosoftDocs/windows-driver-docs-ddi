---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043
title: D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043 (d3d12umddi.h)
description: The D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043 structure retrieves the memory allocation size of a video processor created with the given properties.
ms.date: 05/24/2022
keywords: ["D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043, D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043
targetos: Windows
tech.root: display
f1_keywords:
 - D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043
 - d3d12umddi/D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043
product:
 - Windows
---

# D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043 structure


## -description

Data structure for the [**D3D12DDICAPS_TYPE_VIDEO_0032_PROCESSOR_SIZE**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) capability check when the video feature version is **D3D12DDI_FEATURE_VERSION_VIDEO_0043_0**. Retrieves the memory allocation size of a video processor created with the given properties.

## -struct-fields

### -field VideoProcessorDesc

The creation properties for a video processor heap.  Driver should map these creation properties to size.

### -field MemoryPoolL0Size

The L0 size of the heap object.  Memory Pool L0 is the memory pool “closest” to the GPU.  In the case of UMA adapters, this is the amount of system memory used.  For discrete adapters, this is the amount of discrete memory used.

### -field MemoryPoolL1Size

The L1 size of the heap object.  Memory Pool L1 is the memory pool “second closest” to the GPU.  In the case of UMA adapters, this value is zero.  In the case of discrete adapters, this is the amount of system memory used.

