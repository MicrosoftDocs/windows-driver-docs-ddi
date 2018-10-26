---
UID: NC:d3dkmthk.PFND3DKMT_REMOVESURFACEFROMSWAPCHAIN
title: PFND3DKMT_REMOVESURFACEFROMSWAPCHAIN
author: windows-driver-content
description: Implemented by the client driver to remove a surface from the swap chain.
ms.assetid: ef478dff-62fd-4bcf-905a-b82e58dae8aa
ms.date: 10/19/2018
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
-	PFND3DKMT_REMOVESURFACEFROMSWAPCHAIN
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_REMOVESURFACEFROMSWAPCHAIN callback function

## -description

Implemented by the client driver to remove a surface from the swap chain.

## -prototype

```cpp
//Declaration

PFND3DKMT_REMOVESURFACEFROMSWAPCHAIN Pfnd3dkmtRemovesurfacefromswapchain;

// Definition

NTSTATUS Pfnd3dkmtRemovesurfacefromswapchain
(
	CONST D3DKMT_REMOVESURFACEFROMSWAPCHAIN *
)
{...}

PFND3DKMT_REMOVESURFACEFROMSWAPCHAIN


```

## -parameters

### -param D3DKMT_REMOVESURFACEFROMSWAPCHAIN *

Pointer to a [D3DKMT_REMOVESURFACEFROMSWAPCHAIN](ns-d3dkmthk-_d3dkmt_removesurfacefromswapchain.md) structure that contains the information needed to remove a surface from the swap chain.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_REMOVESURFACEFROMSWAPCHAIN](ns-d3dkmthk-_d3dkmt_removesurfacefromswapchain.md) and then calling Pfnd3dkmtRemoveSurfaceFromSwapChain.

