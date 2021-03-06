---
UID: NC:d3dkmthk.PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA
title: PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA (d3dkmthk.h)
description: Pfnd3dkmtGetresourcepresentprivatedriverdata queries the resource private data, which is associated with the resource during Present.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA callback function"]
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
 - PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA
 - d3dkmthk/PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA
dev_langs:
 - c++
---

# PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA callback function


## -description

Pfnd3dkmtGetresourcepresentprivatedriverdata queries the resource private data, which is associated with the resource during Present.

## -parameters

### -param unnamedParam1

Pointer to a [D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA](../d3dukmdt/ns-d3dukmdt-_d3dddi_getresourcepresentprivatedriverdata.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA Pfnd3dkmtGetresourcepresentprivatedriverdata; 

// Definition

NTSTATUS Pfnd3dkmtGetresourcepresentprivatedriverdata 
(
	D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA *
)
{...}

```

## -remarks

## -see-also

