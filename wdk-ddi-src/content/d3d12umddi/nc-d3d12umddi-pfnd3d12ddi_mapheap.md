---
UID: NC:d3d12umddi.PFND3D12DDI_MAPHEAP
title: PFND3D12DDI_MAPHEAP
author: windows-driver-content
description: Map heap.
ms.assetid: 2187b018-e5d2-4a82-8232-ba9f1ae3a988
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
-	PFND3D12DDI_MAPHEAP
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_MAPHEAP callback function

## -description

Map heap.

## -prototype

```
//Declaration

PFND3D12DDI_MAPHEAP Pfnd3d12ddiMapheap; 

// Definition

HRESULT Pfnd3d12ddiMapheap 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HHEAP
	VOID **
)
{...}

PFND3D12DDI_MAPHEAP 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HHEAP 

A heap handle.

### -param **

Pointer.

## -returns

Returns HRESULT.

## -remarks




## -see-also
