---
UID: NC:d3d12umddi.PFND3D12DDI_RESETCOMMANDALLOCATOR
title: PFND3D12DDI_RESETCOMMANDALLOCATOR
description: Implemented by the client driver to reset the command allocator.
ms.assetid: f706c981-a156-4fa1-96c1-7bb823f6d2d9
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
-	PFND3D12DDI_RESETCOMMANDALLOCATOR
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_RESETCOMMANDALLOCATOR callback function

## -description

Implemented by the client driver to reset the command allocator.

## -prototype

```cpp
//Declaration

PFND3D12DDI_RESETCOMMANDALLOCATOR Pfnd3d12ddiResetcommandallocator; 

// Definition

VOID Pfnd3d12ddiResetcommandallocator 
(
	 D3D12DDI_HCOMMANDALLOCATOR
)
{...}

PFND3D12DDI_RESETCOMMANDALLOCATOR 


```

## -parameters

### -param D3D12DDI_HCOMMANDALLOCATOR: 

A handle to the command allocator.

## -returns

Returns VOID.

## -remarks




## -see-also
