---
UID: NC:d3dkmthk.PFND3DKMT_RELEASEKEYEDMUTEX
title: PFND3DKMT_RELEASEKEYEDMUTEX (d3dkmthk.h)
description: The PFND3DKMT_RELEASEKEYEDMUTEX callback function releases a keyed mutex object.
ms.assetid: a738d7b0-4526-4549-9371-e67036b2eae8
ms.date: 10/19/2018
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
 - "d3dkmthk/PFND3DKMT_RELEASEKEYEDMUTEX"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_RELEASEKEYEDMUTEX
product:
 - Windows
dev_langs:
 - c++
---

# PFND3DKMT_RELEASEKEYEDMUTEX callback function

## -description

The PFND3DKMT_RELEASEKEYEDMUTEX callback function releases a keyed mutex object.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_RELEASEKEYEDMUTEX](ns-d3dkmthk-_d3dkmt_releasekeyedmutex.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_RELEASEKEYEDMUTEX Pfnd3dkmtReleasekeyedmutex; 

// Definition

NTSTATUS Pfnd3dkmtReleasekeyedmutex 
(
	D3DKMT_RELEASEKEYEDMUTEX *
)
{...}

```

## -remarks

## -see-also

