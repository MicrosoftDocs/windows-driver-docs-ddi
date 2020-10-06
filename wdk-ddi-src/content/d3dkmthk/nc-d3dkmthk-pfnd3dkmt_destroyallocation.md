---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYALLOCATION
title: PFND3DKMT_DESTROYALLOCATION (d3dkmthk.h)
description: The PFND3DKMT_DESTROYALLOCATION callback function releases allocations.
ms.assetid: cad9c963-924a-427a-886c-62e0541c0caa
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYALLOCATION callback function"]
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
 - PFND3DKMT_DESTROYALLOCATION
 - d3dkmthk/PFND3DKMT_DESTROYALLOCATION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYALLOCATION
dev_langs:
 - c++
---

# PFND3DKMT_DESTROYALLOCATION callback function


## -description

The PFND3DKMT_DESTROYALLOCATION callback function releases allocations.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_DESTROYALLOCATION](ns-d3dkmthk-_d3dkmt_destroyallocation.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYALLOCATION Pfnd3dkmtDestroyallocation; 

// Definition

NTSTATUS Pfnd3dkmtDestroyallocation 
(
	const D3DKMT_DESTROYALLOCATION *
)
{...}

```

