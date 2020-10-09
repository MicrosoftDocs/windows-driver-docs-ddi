---
UID: NC:d3dkmthk.PFND3DKMT_GETPRESENTHISTORY
title: PFND3DKMT_GETPRESENTHISTORY (d3dkmthk.h)
description: Pfnd3dkmtGetpresenthistory retrieves copying history.
ms.assetid: 1c46273a-6ea5-446e-b4ee-df3213fe9a26
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETPRESENTHISTORY callback function"]
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
 - PFND3DKMT_GETPRESENTHISTORY
 - d3dkmthk/PFND3DKMT_GETPRESENTHISTORY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETPRESENTHISTORY
dev_langs:
 - c++
---

# PFND3DKMT_GETPRESENTHISTORY callback function


## -description

Pfnd3dkmtGetpresenthistory retrieves copying history.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETPRESENTHISTORY](ns-d3dkmthk-_d3dkmt_getpresenthistory.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETPRESENTHISTORY Pfnd3dkmtGetpresenthistory; 

// Definition

NTSTATUS Pfnd3dkmtGetpresenthistory 
(
	D3DKMT_GETPRESENTHISTORY *
)
{...}

```

## -remarks

## -see-also

