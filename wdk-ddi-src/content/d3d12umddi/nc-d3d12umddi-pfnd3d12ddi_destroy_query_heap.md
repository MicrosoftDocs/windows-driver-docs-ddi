---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_QUERY_HEAP
title: PFND3D12DDI_DESTROY_QUERY_HEAP (d3d12umddi.h)
description: Destroys the query heap.
ms.assetid: a99e0330-70bd-450e-8783-15b67b644ee8
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
- PFND3D12DDI_DESTROY_QUERY_HEAP
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_DESTROY_QUERY_HEAP callback function

## -description

Destroys the query heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_QUERY_HEAP Pfnd3d12ddiDestroyQueryHeap; 

// Definition

VOID Pfnd3d12ddiDestroyQueryHeap 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HQUERYHEAP
)
{...}

PFND3D12DDI_DESTROY_QUERY_HEAP 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HQUERYHEAP: 

A query heap handle.

## -returns

Returns VOID.

## -remarks




## -see-also
