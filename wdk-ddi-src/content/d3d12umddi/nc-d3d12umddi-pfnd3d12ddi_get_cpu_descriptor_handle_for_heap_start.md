---
UID: NC:d3d12umddi.PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
title: PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
author: windows-driver-content
description: 
ms.assetid: 1ba126a0-ae78-48f9-9560-3c15d464e390
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	d3d12umddi.h
apiname: 
-	PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START Pfnd3d12ddiGetCpuDescriptorHandleForHeapStart; 

// Definition

D3D12DDI_CPU_DESCRIPTOR_HANDLE Pfnd3d12ddiGetCpuDescriptorHandleForHeapStart 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HDESCRIPTORHEAP
)
{...}

PFND3D12DDI_GET_CPU_DESCRIPTOR_HANDLE_FOR_HEAP_START 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HDESCRIPTORHEAP: 



## -returns

Returns D3D12DDI_CPU_DESCRIPTOR_HANDLE that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also