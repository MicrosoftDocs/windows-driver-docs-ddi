---
UID: NC:d3dkmthk.PFND3DKMT_SETQUEUEDLIMIT
title: PFND3DKMT_SETQUEUEDLIMIT (d3dkmthk.h)
description: The PFND3DKMT_SETQUEUEDLIMIT callback function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.
ms.assetid: 80cfb48c-cc5e-4186-9643-b147d1228701
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETQUEUEDLIMIT"
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
- PFND3DKMT_SETQUEUEDLIMIT
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_SETQUEUEDLIMIT callback function

## -description

The PFND3DKMT_SETQUEUEDLIMIT callback function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.

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

## -parameters

### -param * 

Pointer to a [D3DKMT_SETQUEUEDLIMIT](ns-d3dkmthk-_d3dkmt_setqueuedlimit.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
