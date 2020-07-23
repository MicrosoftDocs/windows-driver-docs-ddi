---
UID: NC:d3dkmthk.PFND3DKMT_GETDISPLAYMODELIST
title: PFND3DKMT_GETDISPLAYMODELIST (d3dkmthk.h)
description: Pfnd3dkmtGetdisplaymodelist retrieves a list of available display modes, including modes with extended format.
ms.assetid: c7171063-216c-4a9e-b586-7fbad6a84357
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETDISPLAYMODELIST callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_GETDISPLAYMODELIST"
 - "PFND3DKMT_GETDISPLAYMODELIST"
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
- PFND3DKMT_GETDISPLAYMODELIST
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_GETDISPLAYMODELIST callback function

## -description

Pfnd3dkmtGetdisplaymodelist retrieves a list of available display modes, including modes with extended format.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETDISPLAYMODELIST Pfnd3dkmtGetdisplaymodelist; 

// Definition

NTSTATUS Pfnd3dkmtGetdisplaymodelist 
(
	D3DKMT_GETDISPLAYMODELIST *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETDISPLAYMODELIST](ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
