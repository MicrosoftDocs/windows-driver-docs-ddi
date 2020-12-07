---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITCOMMANDTOHWQUEUE
title: PFND3DKMT_SUBMITCOMMANDTOHWQUEUE (d3dkmthk.h)
description: Implemented by the client driver to submit a command to queue hardware flags.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SUBMITCOMMANDTOHWQUEUE callback function"]
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
 - PFND3DKMT_SUBMITCOMMANDTOHWQUEUE
 - d3dkmthk/PFND3DKMT_SUBMITCOMMANDTOHWQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SUBMITCOMMANDTOHWQUEUE
product:
 - Windows
---

# PFND3DKMT_SUBMITCOMMANDTOHWQUEUE callback function


## -description

Implemented by the client driver to submit a command to queue hardware flags.

## -parameters

### -param D3DKMT_SUBMITCOMMANDTOHWQUEUE *

Pointer to a [D3DKMT_SUBMITCOMMANDTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitcommandtohwqueue.md) structure that contains information to submit a command to queue hardware flags.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

PFND3DKMT_SUBMITCOMMANDTOHWQUEUE Pfnd3dkmtSubmitcommandtohwqueue;

// Definition

NTSTATUS Pfnd3dkmtSubmitcommandtohwqueue
(
	CONST D3DKMT_SUBMITCOMMANDTOHWQUEUE *
)
{...}

PFND3DKMT_SUBMITCOMMANDTOHWQUEUE


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_SUBMITCOMMANDTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitcommandtohwqueue.md) and then calling Pfnd3dkmtSubmitCommandToHwQueue.

