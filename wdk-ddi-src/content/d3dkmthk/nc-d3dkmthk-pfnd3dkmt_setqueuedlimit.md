---
UID: NC:d3dkmthk.PFND3DKMT_SETQUEUEDLIMIT
title: PFND3DKMT_SETQUEUEDLIMIT (d3dkmthk.h)
description: The PFND3DKMT_SETQUEUEDLIMIT callback function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETQUEUEDLIMIT callback function"]
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
 - PFND3DKMT_SETQUEUEDLIMIT
 - d3dkmthk/PFND3DKMT_SETQUEUEDLIMIT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETQUEUEDLIMIT
dev_langs:
 - c++
---

# PFND3DKMT_SETQUEUEDLIMIT callback function


## -description

The PFND3DKMT_SETQUEUEDLIMIT callback function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_SETQUEUEDLIMIT](ns-d3dkmthk-_d3dkmt_setqueuedlimit.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETQUEUEDLIMIT Pfnd3dkmtSetqueuedlimit; 

// Definition

NTSTATUS Pfnd3dkmtSetqueuedlimit 
(
	const D3DKMT_SETQUEUEDLIMIT *
)
{...}

```

## -remarks

## -see-also

