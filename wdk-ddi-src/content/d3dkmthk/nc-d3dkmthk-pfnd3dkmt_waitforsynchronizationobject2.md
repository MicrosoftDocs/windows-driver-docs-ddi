---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
title: PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 (d3dkmthk.h)
description: The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 callback function inserts a wait for the specified synchronization objects in the specified context stream.
ms.assetid: 452cf763-07c3-4338-ae71-7e7dbd52dc29
ms.date: 10/19/2018
keywords: ["PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2"
 - "PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2"
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
- PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 callback function

## -description

The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 callback function inserts a wait for the specified synchronization objects in the specified context stream.

## -prototype

```cpp
//Declaration

PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 Pfnd3dkmtWaitforsynchronizationobject2; 

// Definition

NTSTATUS Pfnd3dkmtWaitforsynchronizationobject2 
(
	D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
