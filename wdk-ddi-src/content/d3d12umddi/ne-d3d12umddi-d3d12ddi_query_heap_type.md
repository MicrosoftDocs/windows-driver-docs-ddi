---
UID: NE:d3d12umddi.D3D12DDI_QUERY_HEAP_TYPE
title: D3D12DDI_QUERY_HEAP_TYPE
author: windows-driver-content
description: Type of a query heap, which is an array of query results.
old-location: display\d3d12ddi_query_heap_type.htm
ms.assetid: 8A1A42B5-D978-4019-825B-94DB81C44FEA
ms.date: 04/16/2018
ms.keywords: D3D12DDI_QUERY_HEAP_TYPE, D3D12DDI_QUERY_HEAP_TYPE enumeration [Display Devices], D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP, D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION, D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP, display.d3d12ddi_query_heap_type
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_QUERY_HEAP_TYPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_QUERY_HEAP_TYPE
---

# D3D12DDI_QUERY_HEAP_TYPE enumeration


## -description


Type of a query heap, which is an array of query results. Queries are used to capture information from the GPU, such as statistics and status codes which can later be consumed directly on the GPU or on CPU.


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

## -remarks

Queries are an existing D3D12 concept that are used to support retrieving status structures with D3D12DDI_QUERY_HEAP_TYPE_VIDEO_DECODE_STATISTICS and D3D12DDI_QUERY_TYPE_VIDEO_DECODE_STATISTICS. The D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS structure defines the resolved data returned.  This status structure is used for all video decoders.

