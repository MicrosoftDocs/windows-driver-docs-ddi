---
UID: NC:d3dkmthk.PFND3DKMT_ADDSURFACETOSWAPCHAIN
title: PFND3DKMT_ADDSURFACETOSWAPCHAIN
description: Implemented by the client driver to add a surface to the swapchain.
ms.assetid: cad91f7c-de5e-4432-9bb6-0e9b6f5f8902
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
-	PFND3DKMT_ADDSURFACETOSWAPCHAIN
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_ADDSURFACETOSWAPCHAIN callback function

## -description

Implemented by the client driver to add a surface to the swapchain.

## -prototype

```cpp
//Declaration

PFND3DKMT_ADDSURFACETOSWAPCHAIN Pfnd3dkmtAddsurfacetoswapchain;

// Definition

NTSTATUS Pfnd3dkmtAddsurfacetoswapchain
(
	CONST D3DKMT_ADDSURFACETOSWAPCHAIN *
)
{...}

PFND3DKMT_ADDSURFACETOSWAPCHAIN


```

## -parameters

### -param D3DKMT_ADDSURFACETOSWAPCHAIN *

Pointer to a [D3DKMT_ADDSURFACETOSWAPCHAIN](..\d3dkmthk\ns-d3dkmthk-_d3dkmt_addsurfacetoswapchain.md) structure to add a surface to the swapchain.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_ADDSURFACETOSWAPCHAIN](..\d3dkmthk\ns-d3dkmthk-_d3dkmt_addsurfacetoswapchain.md) and then calling Pfnd3dkmtAddSurfaceToSwapchain.

