---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEFENCE
title: PFND3D12DDI_CREATEFENCE
author: windows-driver-content
description: Creates a fence.
ms.assetid: dcfe2112-bb20-4808-9cd3-59aa56875af7
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
-	PFND3D12DDI_CREATEFENCE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATEFENCE callback function

## -description

Creates a fence.

## -prototype

```
//Declaration

PFND3D12DDI_CREATEFENCE Pfnd3d12ddiCreatefence; 

// Definition

HRESULT Pfnd3d12ddiCreatefence 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HFENCE
	CONST D3D12DDIARG_CREATE_FENCE *
)
{...}

PFND3D12DDI_CREATEFENCE 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HFENCE: 

A fence handle.

### -param * 

Pointer to a D3D12DDIARG_CREATE_FENCE structure.

## -returns

Returns HRESULT.
