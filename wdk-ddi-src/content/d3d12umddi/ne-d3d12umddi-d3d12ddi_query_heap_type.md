---
UID: NE:d3d12umddi.D3D12DDI_QUERY_HEAP_TYPE
title: D3D12DDI_QUERY_HEAP_TYPE (d3d12umddi.h)
description: Type of a query heap, which is an array of query results.
old-location: display\d3d12ddi_query_heap_type.htm
ms.date: 05/13/2021
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

### -field D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION

Occlusion.

### -field D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP

Timestamp.

### -field D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS

Pipeline statistics.

### -field D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS

SO statistics.

### -field D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS

Video decode statistics.

### -field D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP

Copy queue timestamp.

### -field D3D12DDI_QUERY_HEAP_TYPE_VIDEO_ENCODE_STATISTICS

For internal use only.

### -field D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS1

[Pipeline statistics](ns-d3d12umddi-d3d12ddi_query_data_pipeline_statistics1.md).

### -field D3D12DDI_QUERY_HEAP_TYPE_JPEG

For internal use only.

## -remarks

Queries are used to capture information from the GPU, such as statistics and status codes which can later be consumed directly on the GPU or on CPU. Status structures associated with the query heap type define the resolved data that is returned.

## -see-also

[**pfnd3d12ddiCreateQueryHeap0001**](../d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_create_query_heap_0001.md)
