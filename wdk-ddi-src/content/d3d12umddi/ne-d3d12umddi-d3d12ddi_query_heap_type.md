---
UID: NE:d3d12umddi.D3D12DDI_QUERY_HEAP_TYPE
title: D3D12DDI_QUERY_HEAP_TYPE (d3d12umddi.h)
description: Type of a query heap, which is an array of query results.
old-location: display\d3d12ddi_query_heap_type.htm
ms.date: 08/22/2022
keywords: ["D3D12DDI_QUERY_HEAP_TYPE enumeration"]
ms.keywords: D3D12DDI_QUERY_HEAP_TYPE, D3D12DDI_QUERY_HEAP_TYPE enumeration [Display Devices], D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP, D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION, D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP, display.d3d12ddi_query_heap_type
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_QUERY_HEAP_TYPE
f1_keywords:
 - D3D12DDI_QUERY_HEAP_TYPE
 - d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_QUERY_HEAP_TYPE
---

# D3D12DDI_QUERY_HEAP_TYPE enumeration

## -description

A **D3D12DDI_QUERY_HEAP_TYPE** enum value identifies the type of a query heap, which is an array of query results.

## -enum-fields

### -field D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION:0

Returns a binary 0/1 result: 0 indicates that no samples passed depth and stencil testing, 1 indicates that at least one sample passed depth and stencil testing. This enables occlusion queries to not interfere with any GPU performance optimization associated with depth/stencil testing.

### -field D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP:1

The heap is for high-performance timing data.

### -field D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS:2

The heap is to contain pre-D3D12 graphics pipeline data. See [**D3D11_DDI_QUERY_DATA_PIPELINE_STATISTICS**](../d3d10umddi/ns-d3d10umddi-d3d11_ddi_query_data_pipeline_statistics.md).

### -field D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS:3

The heap is to contain stream output data. See [**D3D10_DDI_QUERY_DATA_SO_STATISTICS**](../d3d10umddi/ns-d3d10umddi-d3d10_ddi_query_data_so_statistics.md)

### -field D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS:4

The heap is to contain video decode data. See [**D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022**](ns-d3d12umddi-d3d12ddi_query_data_video_decode_statistics_0022.md).

### -field D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP:5

The heap is to contain timestamp queries emitted exclusively by copy command lists. Copy queue timestamps can only be queried from a copy command list, and a copy command list can not emit to a regular timestamp query Heap.

### -field D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS1:7

The heap is to contain pipeline data. See [**D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1**](ns-d3d12umddi-d3d12ddi_query_data_pipeline_statistics1.md).

## -remarks

Queries are used to capture information from the GPU, such as statistics and status codes which can later be consumed directly on the GPU or on CPU. Status structures associated with the query heap type define the resolved data that is returned.

## -see-also

[**pfnd3d12ddiCreateQueryHeap0001**](nc-d3d12umddi-pfnd3d12ddi_create_query_heap_0001.md)
