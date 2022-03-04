---
UID: NS:d3d12umddi.D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2
tech.root: display
title: D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2
f1_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2
 - d3d12umddi/D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2
---

## -description

The **D3D12DDICAPS_VIDEO_ENCODER_HEAP_SIZE_DATA_0080_2** structure is used to retrieve the memory requirements of a video encoder heap.

## -struct-fields

### -field HeapDesc

[in] A [**D3D12DDIARG_CREATE_VIDEO_ENCODER_HEAP_0080_2**](ns-d3d12umddi-d3d12ddiarg_create_video_encoder_heap_0080_2.md) structure that specifies the creation properties for a video encoder heap. The driver should map these creation properties to size and assume the maximum resolution allowed for such a heap.

### -field IsSupported

[out] Indicates whether the given feature values are supported.

### -field MemoryPoolL0Size

[out] The L0 size of the heap object, in bytes. Memory pool L0 is the memory pool "closest" to the GPU. For UMA adapters, this is the amount of system memory used. For discrete adapters, this is the amount of discrete memory used.

### -field MemoryPoolL1Size

[out] The L1 size of the heap object, in bytes. Memory pool L0 is the memory pool "second closest" to the GPU. For UMA adapters, this value is zero. For discrete adapters, this is the amount of system memory used.

## -remarks

The D3D runtime calls [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) with [**D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_HEAP_SIZE**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) specified as the capability type.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)
