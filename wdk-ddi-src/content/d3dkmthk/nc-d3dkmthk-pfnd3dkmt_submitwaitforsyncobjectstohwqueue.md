---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
title: PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE (d3dkmthk.h)
description: Implemented by the client driver to submit a wait on the hardware queue.
ms.assetid: 0f4b3b58-85e3-420f-9e14-9eca73c391b5
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE callback function"]
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
targetos: Windows
tech.root: display
f1_keywords:
 - PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
 - d3dkmthk/PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
product:
 - Windows
---

# PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE callback function


## -description

Implemented by the client driver to submit a wait on the hardware queue.

## -parameters

### -param D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE *

Pointer to a [D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitwaitforsyncobjectstohwqueue.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE Pfnd3dkmtSubmitwaitforsyncobjectstohwqueue;

// Definition

NTSTATUS Pfnd3dkmtSubmitwaitforsyncobjectstohwqueue
(
	CONST D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE *
)
{...}

PFND3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitwaitforsyncobjectstohwqueue.md) and then calling Pfnd3dkmtSubmitwaitforsyncobjectstohwqueue.

