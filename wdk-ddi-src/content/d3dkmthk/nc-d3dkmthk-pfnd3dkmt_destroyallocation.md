---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYALLOCATION
title: PFND3DKMT_DESTROYALLOCATION (d3dkmthk.h)
description: The PFND3DKMT_DESTROYALLOCATION callback function releases allocations.
ms.assetid: cad9c963-924a-427a-886c-62e0541c0caa
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_DESTROYALLOCATION"
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
- PFND3DKMT_DESTROYALLOCATION
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_DESTROYALLOCATION callback function

## -description

The PFND3DKMT_DESTROYALLOCATION callback function releases allocations.

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

## -parameters

### -param *

Pointer to a [D3DKMT_DESTROYALLOCATION](ns-d3dkmthk-_d3dkmt_destroyallocation.md) structure.

## -returns

Returns NTSTATUS.
