---
UID: NC:d3d12umddi.PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
title: PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
author: windows-driver-content
description: 
ms.assetid: bffa5a27-4b90-4fb9-a121-4ecbe4813b10
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START Pfnd3d12ddiGetGpuDescriptorHandleForHeapStart; 

// Definition

D3D12DDI_GPU_DESCRIPTOR_HANDLE Pfnd3d12ddiGetGpuDescriptorHandleForHeapStart 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HDESCRIPTORHEAP
)
{...}

PFND3D12DDI_GET_GPU_DESCRIPTOR_HANDLE_FOR_HEAP_START 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HDESCRIPTORHEAP: 



## -returns

Returns D3D12DDI_GPU_DESCRIPTOR_HANDLE that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also