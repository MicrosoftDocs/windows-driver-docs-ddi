---
UID: NE:d3d12umddi.D3D12DDI_QUERY_TYPE
title: D3D12DDI_QUERY_TYPE
author: windows-driver-content
description: Type of a query.
old-location: display\d3d12ddi_query_type.htm
old-project: display
ms.assetid: C411997A-0F01-4D88-816A-BD375D0744C7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM3, d3d12umddi/D3D12DDI_QUERY_TYPE, D3D12DDI_QUERY_TYPE_BINARY_OCCLUSION, d3d12umddi/D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM2, d3d12umddi/D3D12DDI_QUERY_TYPE_0020_VIDEO_DECODE_STATISTICS, d3d12umddi/D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM0, d3d12umddi/D3D12DDI_QUERY_TYPE_OCCLUSION, d3d12umddi/D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM1, D3D12DDI_QUERY_TYPE_PIPELINE_STATISTICS, D3D12DDI_QUERY_TYPE_OCCLUSION, d3d12umddi/D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM3, d3d12umddi/D3D12DDI_QUERY_TYPE_BINARY_OCCLUSION, D3D12DDI_QUERY_TYPE enumeration [Display Devices], d3d12umddi/D3D12DDI_QUERY_TYPE_PIPELINE_STATISTICS, D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM2, D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM0, D3D12DDI_QUERY_TYPE_TIMESTAMP, D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM1, display.d3d12ddi_query_type, D3D12DDI_QUERY_TYPE, d3d12umddi/D3D12DDI_QUERY_TYPE_TIMESTAMP, D3D12DDI_QUERY_TYPE_0020_VIDEO_DECODE_STATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_QUERY_TYPE
product: Windows
targetos: Windows
req.typenames: D3D12DDI_QUERY_TYPE
---

# D3D12DDI_QUERY_TYPE enumeration


## -description


Type of a query.


## -syntax


````
typedef enum D3D12DDI_QUERY_TYPE { 
  D3D12DDI_QUERY_TYPE_OCCLUSION                     = 0,
  D3D12DDI_QUERY_TYPE_BINARY_OCCLUSION              = 1,
  D3D12DDI_QUERY_TYPE_TIMESTAMP                     = 2,
  D3D12DDI_QUERY_TYPE_PIPELINE_STATISTICS           = 3,
  D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM0         = 4,
  D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM1         = 5,
  D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM2         = 6,
  D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM3         = 7,
  D3D12DDI_QUERY_TYPE_0020_VIDEO_DECODE_STATISTICS  = 8
} D3D12DDI_QUERY_TYPE;
````


## -enum-fields




#### - D3D12DDI_QUERY_TYPE_OCCLUSION

Occlusion.


#### - D3D12DDI_QUERY_TYPE_BINARY_OCCLUSION

Binary occlusion.


#### - D3D12DDI_QUERY_TYPE_TIMESTAMP

Timestamp.


#### - D3D12DDI_QUERY_TYPE_PIPELINE_STATISTICS

Pipeline statistics.


#### - D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM0

SO statistics for Stream0.


#### - D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM1

SO statistics for Stream1.


#### - D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM2

SO statistics for Stream2.


#### - D3D12DDI_QUERY_TYPE_SO_STATISTICS_STREAM3

SO statistics for Stream3.


#### - D3D12DDI_QUERY_TYPE_0020_VIDEO_DECODE_STATISTICS

Video decode statistics.

