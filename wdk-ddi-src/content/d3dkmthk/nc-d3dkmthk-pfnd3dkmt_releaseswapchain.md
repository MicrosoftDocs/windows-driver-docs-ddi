---
UID: NC:d3dkmthk.PFND3DKMT_RELEASESWAPCHAIN
title: PFND3DKMT_RELEASESWAPCHAIN (d3dkmthk.h)
description: The PFND3DKMT_RELEASESWAPCHAIN callback function releases swap chain resources.
ms.assetid: aa7a2119-8f7e-49fa-ad19-efce8c928d03
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_RELEASESWAPCHAIN"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_RELEASESWAPCHAIN
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_RELEASESWAPCHAIN callback function

## -description

The PFND3DKMT_RELEASESWAPCHAIN callback function releases swap chain resources.

## -prototype

```cpp
//Declaration

PFND3DKMT_RELEASESWAPCHAIN Pfnd3dkmtReleaseswapchain; 

// Definition

NTSTATUS Pfnd3dkmtReleaseswapchain 
(
	D3DKMT_RELEASESWAPCHAIN *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_RELEASESWAPCHAIN](ns-d3dkmthk-_d3dkmt_releaseswapchain.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
