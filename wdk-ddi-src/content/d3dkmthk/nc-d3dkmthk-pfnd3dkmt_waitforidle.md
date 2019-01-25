---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORIDLE
title: PFND3DKMT_WAITFORIDLE (d3dkmthk.h)
description: The PFND3DKMT_WAITFORIDLE callback function waits for a display device to be idle.
ms.assetid: a9d632cc-0f23-4a65-a036-afac2739319c
ms.date: 10/19/2018
ms.topic: callback
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_WAITFORIDLE
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_WAITFORIDLE callback function

## -description

The PFND3DKMT_WAITFORIDLE callback function waits for a display device to be idle.

## -prototype

```cpp
//Declaration

PFND3DKMT_WAITFORIDLE Pfnd3dkmtWaitforidle; 

// Definition

NTSTATUS Pfnd3dkmtWaitforidle 
(
	const D3DKMT_WAITFORIDLE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_WAITFORIDLE](ns-d3dkmthk-_d3dkmt_waitforidle.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
