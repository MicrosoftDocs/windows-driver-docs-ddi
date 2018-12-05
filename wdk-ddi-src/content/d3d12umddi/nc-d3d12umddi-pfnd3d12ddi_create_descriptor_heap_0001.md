---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001
title: PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001
author: windows-driver-content
description: Create descriptor heap.
ms.assetid: c60b9860-d115-47ee-aadc-f25c36c789a5
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
-	PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001 callback function

## -description

Create descriptor heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001 Pfnd3d12ddiCreateDescriptorHeap0001; 

// Definition

HRESULT Pfnd3d12ddiCreateDescriptorHeap0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_DESCRIPTOR_HEAP_0001 *
	 D3D12DDI_HDESCRIPTORHEAP
)
{...}

PFND3D12DDI_CREATE_DESCRIPTOR_HEAP_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_CREATE_DESCRIPTOR_HEAP_0001 structure.

### -param D3D12DDI_HDESCRIPTORHEAP

A descriptor heap handle.

## -returns

Returns HRESULT.
