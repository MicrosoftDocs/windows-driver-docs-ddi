---
UID: NC:d3d12umddi.PFND3D12DDI_MAKERESIDENT_CB
title: PFND3D12DDI_MAKERESIDENT_CB (d3d12umddi.h)
description: pfnMakeResidentCb is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_MAKERESIDENT_CB callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3D12DDI_MAKERESIDENT_CB
 - d3d12umddi/PFND3D12DDI_MAKERESIDENT_CB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_MAKERESIDENT_CB
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_MAKERESIDENT_CB callback function


## -description

pfnMakeResidentCb is used to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.

## -parameters

### -param hRTDevice

A handle to the display device to be handled in the runtime.

### -param hRTPagingQueue

A handle to the paging queue to be handled in the runtime.

### -param Arg3

Pointer to a [D3DDDI_MAKERESIDENT](../d3dukmdt/ns-d3dukmdt-d3dddi_makeresident.md) structure.

## -returns

Returns HRESULT.

## -prototype

```cpp
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

