---
UID: NC:d3dkmthk.PFND3DKMT_ABANDONSWAPCHAIN
title: PFND3DKMT_ABANDONSWAPCHAIN (d3dkmthk.h)
description: Abandon the swap chain effect.
ms.assetid: 06eaa290-e47f-446f-9f60-3aba3f31029c
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_ABANDONSWAPCHAIN"
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
- PFND3DKMT_ABANDONSWAPCHAIN
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_ABANDONSWAPCHAIN callback function

## -description

Abandon the swap chain effect.

## -prototype

```cpp
//Declaration

PFND3DKMT_ABANDONSWAPCHAIN Pfnd3dkmtAbandonswapchain; 

// Definition

NTSTATUS Pfnd3dkmtAbandonswapchain 
(
	D3DKMT_ABANDONSWAPCHAIN *
)
{...}

```

## -parameters

### -param *

Pointer to a _D3DKMT_ABANDONSWAPCHAIN structure.

## -returns

Returns NTSTATUS.
