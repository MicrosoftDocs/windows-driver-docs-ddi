---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033
title: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 (d3d12umddi.h)
description: The video decoder heap size data.
old-location: display\d3d12ddi-video-decoder-heap-size-data-0033.htm
ms.assetid: beec0f3e-f87b-408b-8745-14b556254d77
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033, D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033, display.d3d12ddi-video-decoder-heap-size-data-0033
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033"
 - "D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033"
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033
---

# D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0033 structure


## -description


Retrieves the memory allocation size of a video decoder heap created with the given properties. This structure is for the D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE capability check in [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).


## -struct-fields




### -field VideoDecoderHeapDesc

The creation properties for a video decoder heap.  Driver should map these creation properties to size.


### -field MemoryPoolL0Size

The L0 size of the heap object. Memory Pool L0 is the memory pool “closest” to the GPU. In the case of UMA adapters, this is the amount of system memory used. For discrete adapters, this is the amount of discrete memory used.


### -field MemoryPoolL1Size

The L1 size of the heap object. Memory Pool L1 is the memory pool “second closest” to the GPU. In the case of UMA adapters, this value is zero. In the case of discrete adapters, this is the amount of system memory used.

