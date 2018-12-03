---
UID: NC:d3dkmthk.PFND3DKMT_SETALLOCATIONPRIORITY
title: PFND3DKMT_SETALLOCATIONPRIORITY
author: windows-driver-content
description: The PFND3DKMT_SETALLOCATIONPRIORITY callback function sets the priority level of a resource or list of allocations.
ms.assetid: 4cdabc99-d898-449c-b27e-cfd7a7363b54
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
-	PFND3DKMT_SETALLOCATIONPRIORITY
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_SETALLOCATIONPRIORITY callback function

## -description

The PFND3DKMT_SETALLOCATIONPRIORITY callback function sets the priority level of a resource or list of allocations.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETALLOCATIONPRIORITY Pfnd3dkmtSetallocationpriority; 

// Definition

NTSTATUS Pfnd3dkmtSetallocationpriority 
(
	const D3DKMT_SETALLOCATIONPRIORITY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SETALLOCATIONPRIORITY](ns-d3dkmthk-_d3dkmt_setallocationpriority.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
