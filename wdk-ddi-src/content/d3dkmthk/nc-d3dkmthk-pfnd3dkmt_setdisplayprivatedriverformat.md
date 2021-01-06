---
UID: NC:d3dkmthk.PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
title: PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT (d3dkmthk.h)
description: The PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT callback function changes the private-format attribute of a video present source.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT callback function"]
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
 - PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
 - d3dkmthk/PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
dev_langs:
 - c++
---

# PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT callback function


## -description

The PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT callback function changes the private-format attribute of a video present source.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT](ns-d3dkmthk-_d3dkmt_setdisplayprivatedriverformat.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT Pfnd3dkmtSetdisplayprivatedriverformat; 

// Definition

NTSTATUS Pfnd3dkmtSetdisplayprivatedriverformat 
(
	const D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT *
)
{...}

```

## -remarks

## -see-also

