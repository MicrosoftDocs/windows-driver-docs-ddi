---
UID: NC:d3d12umddi.PFND3D12DDI_BEGIN_END_QUERY
title: PFND3D12DDI_BEGIN_END_QUERY (d3d12umddi.h)
description: The pfnBeginEndQuery callback function defines the beginning of the portion of a command list to which a query applies.
tech.root: display
ms.assetid: 2032148a-3b57-4fce-be81-c91bef88fd51
ms.date: 11/28/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_BEGIN_END_QUERY"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header: d3d12umddi.h
req.target-type:
req.target-min-winverclnt: Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_BEGIN_END_QUERY
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_BEGIN_END_QUERY callback function

## -description

The pfnBeginEndQuery callback function defines the beginning of the portion of a command list to which a query applies.

## -prototype

```
//Declaration

PFND3D12DDI_BEGIN_END_QUERY Pfnd3d12ddiBeginEndQuery; 

// Definition

VOID Pfnd3d12ddiBeginEndQuery 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_HQUERYHEAP Arg2
	UINT Arg3
	D3D12DDI_QUERY_TYPE Arg4
)
{...}

```

## -parameters

### -param Arg1

*hCommandList*

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

*hQueryHeap*

The handle of a query heap, which represents an array of query results. The underlying data representation of a query result is IHV dependent in query heaps and opaque to applications.  Query results are stored in a query heap until they are later “resolved” into the API defined format.

### -param Arg3

*StartElement*

The value of the start element.

### -param Arg4

*QueryType*

The type of query. Resolve is used by applications to transform a query result previously stored in a query heap into the API defined format.  The resolved data is stored in a D3D12 buffer.  The results can then be consumed by a shader, predication, or mapped and read on the CPU.

## -remarks

Begin/End query and resolve query are scheduled commands that are processed on the GPU.  There is no defined entry point to allow CPU processing on the query results.

Queries that don’t apply to multiple commands may be defined to only use EndQuery.
For example, if the D3D12DDI_QUERY_TYPE_VIDEO_DECODE_STATISTICS query only applies to the previous DecodeFrame command in the same command list, only EndQuery is used for this query type.


## -see-also
