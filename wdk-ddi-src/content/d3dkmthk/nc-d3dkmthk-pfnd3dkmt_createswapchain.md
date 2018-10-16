---
UID: NC:d3dkmthk.PFND3DKMT_CREATESWAPCHAIN
title: PFND3DKMT_CREATESWAPCHAIN
author: windows-driver-content
description: The PFND3DKMT_CREATESWAPCHAIN callback function creates a swap chain.
ms.assetid: 13aeaa2e-d261-4987-8a71-818af54ddf05
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_CREATESWAPCHAIN
product:
-	Windows
targetos: Windows
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

### -param *

Pointer to a [D3DKMT_CREATESWAPCHAIN](ns-d3dkmthk-_d3dkmt_createswapchain.md) structure.

## -returns

Returns NTSTATUS.
