---
UID: NC:d3d12umddi.PFND3D12DDI_EVICT_CB
title: PFND3D12DDI_EVICT_CB (d3d12umddi.h)
description: PFND3D12DDI_EVICT_CB instructs the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_EVICT_CB callback function"]
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
 - PFND3D12DDI_EVICT_CB
 - d3d12umddi/PFND3D12DDI_EVICT_CB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_EVICT_CB
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_EVICT_CB callback function


## -description

PFND3D12DDI_EVICT_CB instructs the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.

## -parameters

### -param hRTDevice

A handle to the display device.

### -param Arg2

A pointer to a [D3DDDICB_EVICT](../d3dumddi/ns-d3dumddi-d3dddicb_evict.md) structure that describes the memory pages to evict.

## -returns

If this callback function succeeds, it returns S_OK. Otherwise, it returns an **HRESULT** error code.

## -prototype

```cpp
//Declaration

PFND3D12DDI_EVICT_CB Pfnd3d12ddiEvictCb; 

// Definition

HRESULT Pfnd3d12ddiEvictCb 
(
	D3D12DDI_HRTDEVICE hRTDevice
	 const D3DDDICB_EVICT *
)
{...}

```

## -remarks

Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.

## -see-also

