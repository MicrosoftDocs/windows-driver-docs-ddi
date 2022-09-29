---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
title: D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072
ms.date: 05/24/2022
targetos: Windows
tech.root: display
description: The D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072 structure retrieves the memory allocation size of a video processor created with the given properties.
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

**D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0072** is the structure for the [**D3D12DDICAPS_TYPE_VIDEO_0032_PROCESSOR_SIZE**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) capability check when the video feature version is **D3D12DDI_FEATURE_VERSION_VIDEO_0072_0**. It is used to retrieve the memory allocation size of a video processor created with the given properties.

## -struct-fields

### -field NodeMask [in]

The set of GPU nodes. For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field OutputStream [in]

A [**D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032**](ns-d3d12umddi-d3d12ddi_video_process_output_stream_desc_0032.md) structure that describes the output stream properties of the video processor.

### -field pInputStreams [in]

Pointer to **NumInputStreams**  [**D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043**](ns-d3d12umddi-d3d12ddi_video_processor_input_stream_desc_0043.md) structures that describe the input stream properties of the video processor.

### -field NumInputStreams [in]

The number of [**D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043**](ns-d3d12umddi-d3d12ddi_video_processor_input_stream_desc_0043.md) structures that **pInputStreams** points to.

### -field Protected [in]

If TRUE, the video processor is created with a protected resource session and used with protected resources.

### -field MemoryPoolL0Size [out]

The L0 size of the heap object. Memory Pool L0 is the memory pool “closest” to the GPU.  In the case of UMA adapters, this is the amount of system memory used.  For discrete adapters, this is the amount of discrete memory used.

### -field MemoryPoolL1Size [out]

The L1 size of the heap object.  Memory Pool L1 is the memory pool “second closest” to the GPU.  In the case of UMA adapters, this value is zero.  In the case of discrete adapters, this is the amount of system memory used.

## -remarks

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDI_VIDEO_PROCESSOR_SIZE_DATA_0043**](ns-d3d12umddi-d3d12ddi_video_processor_size_data_0043.md)

