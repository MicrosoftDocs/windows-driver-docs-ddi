---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE
title: PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE
author: windows-driver-content
description: Calculate private command allocator size.
ms.assetid: b194948b-29b1-453b-9254-06ae5b40ce96
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
-	PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE callback function

## -description

Calculates private command allocator size.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE Pfnd3d12ddiCalcprivatecommandallocatorsize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatecommandallocatorsize 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATECOMMANDALLOCATOR *
)
{...}

PFND3D12DDI_CALCPRIVATECOMMANDALLOCATORSIZE 


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param *: 

Pointer to a D3D12DDIARG_CREATECOMMANDALLOCATOR structure.

## -returns

Returns SIZE_T.

## -remarks




## -see-also