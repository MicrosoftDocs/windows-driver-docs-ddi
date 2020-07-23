---
UID: NC:d3dkmthk.PFND3DKMT_CREATESWAPCHAIN
title: PFND3DKMT_CREATESWAPCHAIN (d3dkmthk.h)
description: The PFND3DKMT_CREATESWAPCHAIN callback function creates a swap chain.
ms.assetid: 13aeaa2e-d261-4987-8a71-818af54ddf05
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATESWAPCHAIN callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_CREATESWAPCHAIN"
 - "PFND3DKMT_CREATESWAPCHAIN"
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
- PFND3DKMT_CREATESWAPCHAIN
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_CREATESWAPCHAIN callback function

## -description

The PFND3DKMT_CREATESWAPCHAIN callback function creates a swap chain.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATESWAPCHAIN Pfnd3dkmtCreateswapchain; 

// Definition

NTSTATUS Pfnd3dkmtCreateswapchain 
(
	D3DKMT_CREATESWAPCHAIN *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_CREATESWAPCHAIN](ns-d3dkmthk-_d3dkmt_createswapchain.md) structure.

## -returns

Returns NTSTATUS.
