---
UID: NC:d3d12umddi.PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
title: PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
description: Gets the CPU descriptor handle that represents the start of the heap.
ms.assetid: 1ba126a0-ae78-48f9-9560-3c15d464e390
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
-	PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START callback function

## -description

Gets the CPU descriptor handle that represents the start of the heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START Pfnd3d12ddiGetCpuDescriptorHandleForHeapStart; 

// Definition

D3D12DDI_CPU_DESCRIPTOR_HANDLE Pfnd3d12ddiGetCpuDescriptorHandleForHeapStart 
(
	 D3D12DDI_HDEVICE hDevice
	 D3D12DDI_HDESCRIPTORHEAP
)
{...}

PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START 


```

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param D3D12DDI_HDESCRIPTORHEAP

A user mode driver handle type.

## -returns

Returns D3D12DDI_CPU_DESCRIPTOR_HANDLE that represents the start of the heap.


## -see-also
