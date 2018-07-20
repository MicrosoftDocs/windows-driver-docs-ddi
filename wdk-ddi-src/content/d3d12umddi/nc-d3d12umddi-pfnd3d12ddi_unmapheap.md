---
UID: NC:d3d12umddi.PFND3D12DDI_UNMAPHEAP
title: PFND3D12DDI_UNMAPHEAP
author: windows-driver-content
description: 
ms.assetid: ff2743ac-ae14-4c19-836a-d8a869b3ff9b
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
-	PFND3D12DDI_UNMAPHEAP
product: Windows
targetos: Windows
---

# PFND3D12DDI_UNMAPHEAP callback function

## -description

Implemented by the client driver to ... 

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

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HHEAP: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also