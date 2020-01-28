---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITPRESENTBLTTOHWQUEUE
title: PFND3DKMT_SUBMITPRESENTBLTTOHWQUEUE (d3dkmthk.h)
description: Implemented by the client driver to submit a present Blt to hardware queue.
ms.assetid: 779315a3-96ce-493a-82b3-63c8b9d289c3
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SUBMITPRESENTBLTTOHWQUEUE"
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
- PFND3DKMT_SUBMITPRESENTBLTTOHWQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_SUBMITPRESENTBLTTOHWQUEUE callback function

## -description

Implemented by the client driver to submit a present Blt to hardware queue.

## -prototype

```cpp
//Declaration

PFND3DKMT_SUBMITPRESENTBLTTOHWQUEUE Pfnd3dkmtSubmitpresentblttohwqueue;

// Definition

NTSTATUS Pfnd3dkmtSubmitpresentblttohwqueue
(
	CONST D3DKMT_SUBMITPRESENTBLTTOHWQUEUE *
)
{...}

PFND3DKMT_SUBMITPRESENTBLTTOHWQUEUE


```

## -parameters

### -param D3DKMT_SUBMITPRESENTBLTTOHWQUEUE *

Pointer to a [D3DKMT_SUBMITPRESENTBLTTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitpresentblttohwqueue.md) structure that contains information to submit a present Blt to hardware queue.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_SUBMITPRESENTBLTTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitpresentblttohwqueue.md) and then calling Pfnd3dkmtSubmitpresentblttohwqueue.

