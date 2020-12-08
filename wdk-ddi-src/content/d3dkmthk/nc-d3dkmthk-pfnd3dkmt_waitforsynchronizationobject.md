---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT
title: PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT callback function inserts a wait for the specified synchronization objects in the specified context stream.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT callback function"]
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
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT
 - d3dkmthk/PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT
dev_langs:
 - c++
---

# PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT callback function


## -description

The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT callback function inserts a wait for the specified synchronization objects in the specified context stream.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT Pfnd3dkmtWaitforsynchronizationobject; 

// Definition

NTSTATUS Pfnd3dkmtWaitforsynchronizationobject 
(
	D3DKMT_WAITFORSYNCHRONIZATIONOBJECT *
)
{...}

```

## -remarks

## -see-also

