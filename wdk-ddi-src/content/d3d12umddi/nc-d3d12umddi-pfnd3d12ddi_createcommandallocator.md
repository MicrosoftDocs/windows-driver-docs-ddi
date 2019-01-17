---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDALLOCATOR
title: PFND3D12DDI_CREATECOMMANDALLOCATOR
description: Creates a command allocator.
ms.assetid: 78393c5e-a99a-4b55-8302-76137bc4f4e5
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
-	PFND3D12DDI_CREATECOMMANDALLOCATOR
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATECOMMANDALLOCATOR callback function

## -description

Creates a command allocator.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATECOMMANDALLOCATOR Pfnd3d12ddiCreatecommandallocator; 

// Definition

HRESULT Pfnd3d12ddiCreatecommandallocator 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATECOMMANDALLOCATOR *
)
{...}

PFND3D12DDI_CREATECOMMANDALLOCATOR 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_CREATECOMMANDALLOCATOR structure.

## -returns

Returns HRESULT.
