---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYCOMMANDALLOCATOR
title: PFND3D12DDI_DESTROYCOMMANDALLOCATOR
author: windows-driver-content
description: Destroys a command allocator.
ms.assetid: c2d78cd5-3273-42eb-b069-bafdea236115
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
-	PFND3D12DDI_DESTROYCOMMANDALLOCATOR
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_DESTROYCOMMANDALLOCATOR callback function

## -description

Destroys a command allocator.

## -prototype

```
//Declaration

PFND3D12DDI_DESTROYCOMMANDALLOCATOR Pfnd3d12ddiDestroycommandallocator; 

// Definition

VOID Pfnd3d12ddiDestroycommandallocator 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDALLOCATOR
)
{...}

PFND3D12DDI_DESTROYCOMMANDALLOCATOR 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HCOMMANDALLOCATOR: 

A handle to a command allocator.

## -returns

Returns VOID.

## -remarks




## -see-also
