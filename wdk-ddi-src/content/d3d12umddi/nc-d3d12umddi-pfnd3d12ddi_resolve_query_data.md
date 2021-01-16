---
UID: NC:d3d12umddi.PFND3D12DDI_RESOLVE_QUERY_DATA
title: PFND3D12DDI_RESOLVE_QUERY_DATA (d3d12umddi.h)
description: The pfnResolveQueryData callback function transforms a previously stored query into an API defined format.
old-location: display\pfnd3d12ddi_resolve_query_data.htm
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_RESOLVE_QUERY_DATA callback function"]
ms.keywords: PFND3D12DDI_RESOLVE_QUERY_DATA, PFND3D12DDI_RESOLVE_QUERY_DATA callback, d3d12umddi/pfnResolveQueryData, display.pfnd3d12ddi_resolve_query_data, pfnResolveQueryData, pfnResolveQueryData callback function [Display Devices]
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
req.typenames: 
f1_keywords:
 - PFND3D12DDI_RESOLVE_QUERY_DATA
 - d3d12umddi/PFND3D12DDI_RESOLVE_QUERY_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_RESOLVE_QUERY_DATA
---

# PFND3D12DDI_RESOLVE_QUERY_DATA callback function


## -description

The <i>pfnResolveQueryData</i> callback function transforms a previously stored query into an API defined format.

## -parameters

### -param Arg1

hCommandList

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

hQueryHeap

The handle of a query heap.

### -param Arg3

QueryType

A query type.

### -param StartElement

The value of the start element.

### -param ElementCount

The element count.

### -param hDrvDestinationBuffer

The handle of a destination buffer.

### -param DestinationOffset

The destination offset.

## -remarks

Resolve functionality is used by applications to transform a query result previously stored in a query heap into the API defined format.  The resolved data is stored in a buffer.  The results can then be consumed by a shader, predication, or mapped and read on the CPU.

