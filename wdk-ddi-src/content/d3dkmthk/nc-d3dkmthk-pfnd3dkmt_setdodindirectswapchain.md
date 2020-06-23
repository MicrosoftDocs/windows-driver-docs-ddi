---
UID: NC:d3dkmthk.PFND3DKMT_SETDODINDIRECTSWAPCHAIN
title: PFND3DKMT_SETDODINDIRECTSWAPCHAIN (d3dkmthk.h)
description: The PFND3DKMT_SETDODINDIRECTSWAPCHAIN callback function sets indirect swap chain resources.
ms.assetid: 51e5a965-48a0-4a1b-a4a9-5b6f590b30c2
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETDODINDIRECTSWAPCHAIN callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETDODINDIRECTSWAPCHAIN"
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
- PFND3DKMT_SETDODINDIRECTSWAPCHAIN
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETDODINDIRECTSWAPCHAIN callback function

## -description

The PFND3DKMT_SETDODINDIRECTSWAPCHAIN callback function sets indirect swap chain resources.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETDODINDIRECTSWAPCHAIN Pfnd3dkmtSetdodindirectswapchain; 

// Definition

NTSTATUS Pfnd3dkmtSetdodindirectswapchain 
(
	D3DKMT_SETDODINDIRECTSWAPCHAIN *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETDODINDIRECTSWAPCHAIN](ns-d3dkmthk-_d3dkmt_setdodindirectswapchain.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
