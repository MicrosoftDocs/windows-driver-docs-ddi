---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP
title: PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP
author: windows-driver-content
description: Destroys the descriptor heap.
ms.assetid: 05e4e853-9d81-4945-b223-a66e076bbac2
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP callback function

## -description

Destroys the descriptor heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP Pfnd3d12ddiDestroyDescriptorHeap; 

// Definition

VOID Pfnd3d12ddiDestroyDescriptorHeap 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HDESCRIPTORHEAP
)
{...}

PFND3D12DDI_DESTROY_DESCRIPTOR_HEAP 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HDESCRIPTORHEAP: 

A descriptor heap handle.

## -returns

Returns VOID.
