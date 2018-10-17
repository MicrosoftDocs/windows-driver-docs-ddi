---
UID: NC:d3d12umddi.PFND3D12DDI_UNMAPHEAP
title: PFND3D12DDI_UNMAPHEAP
author: windows-driver-content
description: Implemented by the client driver to unmap a heap.
ms.assetid: ff2743ac-ae14-4c19-836a-d8a869b3ff9b
ms.date: 
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_UNMAPHEAP
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_UNMAPHEAP callback function

## -description

Implemented by the client driver to unmap a heap.

## -prototype

```
//Declaration

PFND3D12DDI_UNMAPHEAP Pfnd3d12ddiUnmapheap; 

// Definition

VOID Pfnd3d12ddiUnmapheap 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HHEAP
)
{...}

PFND3D12DDI_UNMAPHEAP 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HHEAP 

A heap handle.

## -returns

Returns VOID.

## -remarks




## -see-also
