---
UID: NC:d3dkmthk.PFND3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
title: PFND3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
author: windows-driver-content
description: Implemented by the client driver to open a keyed mutex from an NT handle to the process.
ms.assetid: a09976ec-ba90-4f25-9ffa-c39fdfaa4ac2
ms.date:
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
-	PFND3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_OPENKEYEDMUTEXFROMNTHANDLE callback function

## -description

Implemented by the client driver to open a keyed mutex from an NT handle to the process.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENKEYEDMUTEXFROMNTHANDLE Pfnd3dkmtOpenkeyedmutexfromnthandle;

// Definition

NTSTATUS Pfnd3dkmtOpenkeyedmutexfromnthandle
(
	D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE *
)
{...}

PFND3DKMT_OPENKEYEDMUTEXFROMNTHANDLE


```

## -parameters

### -param D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE*

Pointer to a [D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE](ns-d3dkmthk-_d3dkmt_openkeyedmutexfromnthandle.md) structure that contains information to open a keyed mutex from NT handle.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE](ns-d3dkmthk-_d3dkmt_openkeyedmutexfromnthandle.md) and then calling Pfnd3dkmtOpenKeyedMutexFromNtHandle.

