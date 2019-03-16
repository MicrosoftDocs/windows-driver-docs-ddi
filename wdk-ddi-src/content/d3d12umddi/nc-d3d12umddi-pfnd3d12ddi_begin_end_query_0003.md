---
UID: NC:d3d12umddi.PFND3D12DDI_BEGIN_END_QUERY_0003
title: PFND3D12DDI_BEGIN_END_QUERY_0003 (d3d12umddi.h)
description: The pfnBeginQuery callback function defines the beginning of the portion of a command list to which a query applies.
old-location: display\pfnd3d12ddi_begin_end_query_0003.htm
ms.assetid: 9EBF7E0C-BF6D-4E99-B289-8C6581A2DEA5
ms.date: 04/16/2018
ms.keywords: PFND3D12DDI_BEGIN_END_QUERY_0003, PFND3D12DDI_BEGIN_END_QUERY_0003 callback, d3d12umddi/pfnBeginQuery, display.pfnd3d12ddi_begin_end_query_0003, pfnBeginQuery, pfnBeginQuery callback function [Display Devices]
ms.topic: callback
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnBeginQuery
product:
- Windows
targetos: Windows
tech.root: display
req.typenames:
---

# PFND3D12DDI_BEGIN_END_QUERY_0003 callback function


## -description


The <i>pfnBeginQuery</i> callback function defines the beginning of the portion of a command list to which a query applies.


## -parameters




### -param Arg1

*hCommandList*

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

*hQueryHeap*

The handle of a query heap, which represents an array of query results. The underlying data representation of a query result is IHV dependent in query heaps and opaque to applications.  Query results are stored in a query heap until they are later “resolved” into the API defined format.

### -param Arg3

*QueryType*

The type of query. Resolve is used by applications to transform a query result previously stored in a query heap into the API defined format.  The resolved data is stored in a D3D12 buffer.  The results can then be consumed by a shader, predication, or mapped and read on the CPU.

### -param Arg4

*StartElement*

The value of the start element.

## -returns



This callback function does not return a value.

## -remarks

Begin/End query and resolve query are scheduled commands that are processed on the GPU.  There is no defined entry point to allow CPU processing on the query results.

Queries that don’t apply to multiple commands may be defined to only use EndQuery.
For example, if the D3D12DDI_QUERY_TYPE_VIDEO_DECODE_STATISTICS query only applies to the previous DecodeFrame command in the same command list, only EndQuery is used for this query type.


