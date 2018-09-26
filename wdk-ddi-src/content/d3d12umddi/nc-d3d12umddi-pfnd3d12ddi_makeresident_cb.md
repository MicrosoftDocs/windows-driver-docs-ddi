---
UID: NC:d3d12umddi.PFND3D12DDI_MAKERESIDENT_CB
title: PFND3D12DDI_MAKERESIDENT_CB
author: windows-driver-content
description: pfnMakeResidentCb is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
ms.assetid: 77df8a7f-140c-44f3-ba77-c80c102dbc7e
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
-	PFND3D12DDI_MAKERESIDENT_CB
product:
- Windows
targetos: Windows
---

# PFND3D12DDI_MAKERESIDENT_CB callback function

## -description

pfnMakeResidentCb is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.

## -prototype

```
//Declaration

PFND3D12DDI_MAKERESIDENT_CB Pfnd3d12ddiMakeresidentCb; 

// Definition

HRESULT Pfnd3d12ddiMakeresidentCb 
(
	D3D12DDI_HRTDEVICE hRTDevice
	D3D12DDI_HRTPAGINGQUEUE hRTPagingQueue
	D3DDDI_MAKERESIDENT *
)
{...}

```

## -parameters

### -param hRTDevice

A handle to the display device to be handled in the runtime.

### -param hRTPagingQueue

A handle to the paging queue to be handled in the runtime.

### -param *

Pointer to a [D3DDDI_MAKERESIDENT](../d3dukmdt/ns-d3dukmdt-d3dddi_makeresident.md) structure.


## -returns

Returns HRESULT.