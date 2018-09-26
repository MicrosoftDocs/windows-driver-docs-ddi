---
UID: NC:d3d12umddi.PFND3D12DDI_MAKERESIDENT_0001
title: PFND3D12DDI_MAKERESIDENT_0001
author: windows-driver-content
description: pfnMakeResident is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
ms.assetid: d31a9aac-08c6-44a9-918e-81db909a6f44
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
---

# PFND3D12DDI_MAKERESIDENT_0001 callback function

## -description

pfnMakeResident is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.

## -prototype

```
//Declaration

PFND3D12DDI_MAKERESIDENT_0001 Pfnd3d12ddiMakeresident0001; 

// Definition

HRESULT Pfnd3d12ddiMakeresident0001 
(
	D3D12DDI_HDEVICE Arg1
	D3D12DDIARG_MAKERESIDENT_0001 *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device.

### -param *: 

A pointer to a [D3D12DDIARG_MAKERESIDENT_0001](ns-d3d12umddi-d3d12ddiarg_makeresident_0001.md) structure that describes the memory pages to make resident. 


## -returns

Returns HRESULT.
