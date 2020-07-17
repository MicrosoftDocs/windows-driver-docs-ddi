---
UID: NC:d3dkmthk.PFND3DKMT_CREATEHWQUEUE
title: PFND3DKMT_CREATEHWQUEUE (d3dkmthk.h)
description: Implemented by the client driver to create a new hardware queue.
ms.assetid: 0c8c359a-2c16-4844-a9ec-4a1716f3e980
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATEHWQUEUE callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_CREATEHWQUEUE"
 - "PFND3DKMT_CREATEHWQUEUE"
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
- PFND3DKMT_CREATEHWQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_CREATEHWQUEUE callback function

## -description

Implemented by the client driver to create a new hardware queue.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATEHWQUEUE Pfnd3dkmtCreatehwqueue;

// Definition

NTSTATUS Pfnd3dkmtCreatehwqueue
(
	D3DKMT_CREATEHWQUEUE *
)
{...}

PFND3DKMT_CREATEHWQUEUE


```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_CREATEHWQUEUE](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createhwqueue.md) structure that contains information needed to create a new hardware queue.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_CREATEHWQUEUE](../d3dkmthk/ns-d3dkmthk-_d3dkmt_createhwqueue.md) and then calling Pfnd3dkmtCreateHwQueue.

