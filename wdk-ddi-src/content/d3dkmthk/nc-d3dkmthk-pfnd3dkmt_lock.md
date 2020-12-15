---
UID: NC:d3dkmthk.PFND3DKMT_LOCK
title: PFND3DKMT_LOCK (d3dkmthk.h)
description: Pfnd3dkmtLock locks an entire allocation or specific pages within an allocation.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_LOCK callback function"]
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
 - PFND3DKMT_LOCK
 - d3dkmthk/PFND3DKMT_LOCK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_LOCK
dev_langs:
 - c++
---

# PFND3DKMT_LOCK callback function


## -description

Pfnd3dkmtLock locks an entire allocation or specific pages within an allocation.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_LOCK](ns-d3dkmthk-_d3dkmt_lock.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_LOCK Pfnd3dkmtLock; 

// Definition

NTSTATUS Pfnd3dkmtLock 
(
	D3DKMT_LOCK *
)
{...}

```

## -remarks

## -see-also

