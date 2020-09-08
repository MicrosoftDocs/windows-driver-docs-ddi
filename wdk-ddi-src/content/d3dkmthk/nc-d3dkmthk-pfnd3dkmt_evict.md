---
UID: NC:d3dkmthk.PFND3DKMT_EVICT
title: PFND3DKMT_EVICT (d3dkmthk.h)
description: The Pfnd3dkmtEvict instructs the OS to decrement the residency reference count.
ms.assetid: ef46edbc-aebc-465a-90fc-7087b7fc857b
ms.date: 10/19/2018
keywords: ["PFND3DKMT_EVICT callback function"]
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
 - PFND3DKMT_EVICT
 - d3dkmthk/PFND3DKMT_EVICT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_EVICT
dev_langs:
 - c++
---

# PFND3DKMT_EVICT callback function


## -description

The Pfnd3dkmtEvict instructs the OS to decrement the residency reference count.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_EVICT](ns-d3dkmthk-_d3dkmt_evict.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_EVICT Pfnd3dkmtEvict; 

// Definition

NTSTATUS Pfnd3dkmtEvict 
(
	D3DKMT_EVICT *
)
{...}

```

## -remarks

## -see-also

