---
UID: NC:d3d12umddi.PFND3D12DDI_EVICT2
title: PFND3D12DDI_EVICT2
author: windows-driver-content
description: PFND3D12DDI_EVICT2 instructs the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
ms.assetid: 2ebce9ab-3827-4fa4-848f-58c9eb10f82a
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
-	PFND3D12DDI_EVICT2
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_EVICT2 callback function

## -description

PFND3D12DDI_EVICT2 instructs the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.

## -prototype

```
//Declaration

PFND3D12DDI_EVICT2 Pfnd3d12ddiEvict2; 

// Definition

HRESULT Pfnd3d12ddiEvict2 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_EVICT *
)
{...}

PFND3D12DDI_EVICT2 


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device.

### -param * 

A pointer to a [D3D12DDIARG_EVICT](ns-d3d12umddi-d3d12ddiarg_evict.md) structure that describes the memory pages to evict.

## -returns

If this callback function succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.

## -see-also