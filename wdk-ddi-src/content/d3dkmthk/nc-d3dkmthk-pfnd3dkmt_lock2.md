---
UID: NC:d3dkmthk.PFND3DKMT_LOCK2
title: PFND3DKMT_LOCK2 (d3dkmthk.h)
description: Pfnd3dkmtLock2 locks an entire allocation or specific pages within an allocation.
ms.assetid: d06f98d8-dec7-4330-b3de-845205cf1ca3
ms.date: 10/19/2018
keywords: ["PFND3DKMT_LOCK2 callback function"]
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
 - PFND3DKMT_LOCK2
 - d3dkmthk/PFND3DKMT_LOCK2
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_LOCK2
dev_langs:
 - c++
---

# PFND3DKMT_LOCK2 callback function


## -description

Pfnd3dkmtLock2 locks an entire allocation or specific pages within an allocation.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_LOCK2](ns-d3dkmthk-_d3dkmt_lock2.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_LOCK2 Pfnd3dkmtLock2; 

// Definition

NTSTATUS Pfnd3dkmtLock2 
(
	D3DKMT_LOCK2 *
)
{...}

```

## -remarks

## -see-also

