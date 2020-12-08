---
UID: NC:d3dkmthk.PFND3DKMT_MAKERESIDENT
title: PFND3DKMT_MAKERESIDENT (d3dkmthk.h)
description: Pfnd3dkmtMakeresident adds a resource to the device residency list and increment the residency reference count on this allocation.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_MAKERESIDENT callback function"]
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
 - PFND3DKMT_MAKERESIDENT
 - d3dkmthk/PFND3DKMT_MAKERESIDENT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_MAKERESIDENT
dev_langs:
 - c++
---

# PFND3DKMT_MAKERESIDENT callback function


## -description

Pfnd3dkmtMakeresident adds a resource to the device residency list and increment the residency reference count on this allocation.

## -parameters

### -param Arg1

Pointer to a [D3DDDI_MAKERESIDENT](../d3dukmdt/ns-d3dukmdt-d3dddi_makeresident.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_MAKERESIDENT Pfnd3dkmtMakeresident; 

// Definition

NTSTATUS Pfnd3dkmtMakeresident 
(
	D3DDDI_MAKERESIDENT *
)
{...}

```

## -remarks

## -see-also

