---
UID: NC:d3dkmthk.PFND3DKMT_OPENSWAPCHAIN
title: PFND3DKMT_OPENSWAPCHAIN
author: windows-driver-content
description: PfnOpenSwapChain opens a swap chain.
ms.assetid: 540df885-7b52-4ebd-ac36-5c3d1920919a
ms.date: 
ms.topic: callback
req.header: d3dkmthk.h
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
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_OPENSWAPCHAIN
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_OPENSWAPCHAIN callback function

## -description

PfnOpenSwapChain opens a swap chain.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENSWAPCHAIN Pfnd3dkmtOpenswapchain; 

// Definition

NTSTATUS Pfnd3dkmtOpenswapchain 
(
	D3DKMT_OPENSWAPCHAIN *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENSWAPCHAIN](ns-d3dkmthk-_d3dkmt_openswapchain.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
