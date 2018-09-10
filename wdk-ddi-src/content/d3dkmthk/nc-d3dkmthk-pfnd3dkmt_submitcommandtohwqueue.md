---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITCOMMANDTOHWQUEUE
title: PFND3DKMT_SUBMITCOMMANDTOHWQUEUE
author: windows-driver-content
description: Implemented by the client driver to submit a command to queue hardware flags.
ms.assetid: 4d21d4b5-4b23-44d0-be9c-25d2abbcf628
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
-	PFND3DKMT_SUBMITCOMMANDTOHWQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_SUBMITCOMMANDTOHWQUEUE callback function

## -description

Implemented by the client driver to submit a command to queue hardware flags.

## -prototype

```
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

## -parameters

### -param D3DKMT_SUBMITCOMMANDTOHWQUEUE *

Pointer to a [D3DKMT_SUBMITCOMMANDTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitcommandtohwqueue.md) structure that contains information to submit a command to queue hardware flags.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_SUBMITCOMMANDTOHWQUEUE](ns-d3dkmthk-_d3dkmt_submitcommandtohwqueue.md) and then calling Pfnd3dkmtSubmitCommandToHwQueue.

