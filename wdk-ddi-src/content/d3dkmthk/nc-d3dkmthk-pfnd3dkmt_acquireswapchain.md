---
UID: NC:d3dkmthk.PFND3DKMT_ACQUIRESWAPCHAIN
title: PFND3DKMT_ACQUIRESWAPCHAIN
author: windows-driver-content
description: The PFND3DKMT_ACQUIRESWAPCHAIN callback function acquires a swap chain.
ms.assetid: a657e5a6-68e1-484b-8724-533887a417cf
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
-	PFND3DKMT_ACQUIRESWAPCHAIN
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_ACQUIRESWAPCHAIN callback function

## -description

The PFND3DKMT_ACQUIRESWAPCHAIN callback function acquires a swap chain.

## -prototype

```
//Declaration

PFND3DKMT_ACQUIRESWAPCHAIN Pfnd3dkmtAcquireswapchain; 

// Definition

NTSTATUS Pfnd3dkmtAcquireswapchain 
(
	D3DKMT_ACQUIRESWAPCHAIN *
)
{...}

```

## -parameters

### -param *

Pointer to a [D3DKMT_ACQUIRESWAPCHAIN](ns-d3dkmthk-_d3dkmt_acquireswapchain.md) structure.

## -returns

Returns NTSTATUS.