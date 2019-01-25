---
UID: NC:d3dkmthk.PFND3DKMT_SETSTABLEPOWERSTATE
title: PFND3DKMT_SETSTABLEPOWERSTATE (d3dkmthk.h)
description: The PFND3DKMT_SETSTABLEPOWERSTATE callback function sets stable power state.
ms.assetid: aa8f5012-ea44-46a1-923d-1649632d6656
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
-	PFND3DKMT_SETSTABLEPOWERSTATE
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_SETSTABLEPOWERSTATE callback function

## -description

The PFND3DKMT_SETSTABLEPOWERSTATE callback function sets stable power state.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETSTABLEPOWERSTATE Pfnd3dkmtSetstablepowerstate; 

// Definition

NTSTATUS Pfnd3dkmtSetstablepowerstate 
(
	const D3DKMT_SETSTABLEPOWERSTATE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SETSTABLEPOWERSTATE](ns-d3dkmthk-_d3dkmt_setstablepowerstate.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
