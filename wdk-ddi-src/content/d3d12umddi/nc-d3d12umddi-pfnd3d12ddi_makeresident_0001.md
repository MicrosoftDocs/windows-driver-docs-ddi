---
UID: NC:d3d12umddi.PFND3D12DDI_MAKERESIDENT_0001
title: PFND3D12DDI_MAKERESIDENT_0001
author: windows-driver-content
description: Make resident.
ms.assetid: 2b3e5e59-420c-4107-be13-bb225b0d640a
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
-	PFND3D12DDI_MAKERESIDENT_0001
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_MAKERESIDENT_0001 callback function

## -description

Make resident.

## -prototype

```
//Declaration

PFND3D12DDI_MAKERESIDENT_0001 Pfnd3d12ddiMakeresident0001; 

// Definition

HRESULT Pfnd3d12ddiMakeresident0001 
(
	 D3D12DDI_HDEVICE
	D3D12DDIARG_MAKERESIDENT_0001 *
)
{...}

PFND3D12DDI_MAKERESIDENT_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_MAKERESIDENT_0001 structure.

## -returns

Returns HRESULT.

## -remarks




## -see-also