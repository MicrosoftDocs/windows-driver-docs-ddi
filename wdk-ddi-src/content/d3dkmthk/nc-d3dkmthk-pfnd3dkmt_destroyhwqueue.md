---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYHWQUEUE
title: PFND3DKMT_DESTROYHWQUEUE (d3dkmthk.h)
description: Implemented by the client driver to destroy a hardware queue.
ms.assetid: 4ac646f8-e8c2-4682-bbab-0e91a782e59a
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYHWQUEUE callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_DESTROYHWQUEUE"
 - "PFND3DKMT_DESTROYHWQUEUE"
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
- PFND3DKMT_DESTROYHWQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_DESTROYHWQUEUE callback function

## -description

Implemented by the client driver to destroy a hardware queue.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYHWQUEUE Pfnd3dkmtDestroyhwqueue;

// Definition

NTSTATUS Pfnd3dkmtDestroyhwqueue
(
	CONST D3DKMT_DESTROYHWQUEUE *
)
{...}

PFND3DKMT_DESTROYHWQUEUE


```

## -parameters

### -param D3DKMT_DESTROYHWQUEUE *

Pointer to a [D3DKMT_DESTROYHWQUEUE](ns-d3dkmthk-_d3dkmt_destroyhwqueue.md) structure that contains the information needed to destroy a hardware queue.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_DESTROYHWQUEUE](ns-d3dkmthk-_d3dkmt_destroyhwqueue.md) and then calling PfnD3dkmtDestroyHwQueue.

