---
UID: NC:d3dkmthk.PFND3DKMT_UNORDEREDPRESENTSWAPCHAIN
title: PFND3DKMT_UNORDEREDPRESENTSWAPCHAIN
author: windows-driver-content
description:
ms.assetid: 0de92381-b602-4ae5-adf2-eba28814fe72
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
-	PFND3DKMT_UNORDEREDPRESENTSWAPCHAIN
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_UNORDEREDPRESENTSWAPCHAIN callback function

## -description

Implemented by the client driver to store information about the swap chain being presented.

## -prototype

```
//Declaration

PFND3DKMT_UNORDEREDPRESENTSWAPCHAIN Pfnd3dkmtUnorderedpresentswapchain;

// Definition

NTSTATUS Pfnd3dkmtUnorderedpresentswapchain
(
	CONST D3DKMT_UNORDEREDPRESENTSWAPCHAIN *
)
{...}

PFND3DKMT_UNORDEREDPRESENTSWAPCHAIN


```

## -parameters

### -param D3DKMT_UNORDEREDPRESENTSWAPCHAIN *

Pointer to a [D3DKMT_UNORDEREDPRESENTSWAPCHAIN](ns-d3dkmthk-_d3dkmt_unorderedpresentswapchain.md) structure.

## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_UNORDEREDPRESENTSWAPCHAIN](ns-d3dkmthk-_d3dkmt_unorderedpresentswapchain.md) and then calling Pfnd3dkmtUnorderedpresentswapchain.

