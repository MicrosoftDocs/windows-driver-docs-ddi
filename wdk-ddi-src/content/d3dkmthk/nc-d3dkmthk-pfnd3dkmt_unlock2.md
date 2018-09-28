---
UID: NC:d3dkmthk.PFND3DKMT_UNLOCK2
title: PFND3DKMT_UNLOCK2
author: windows-driver-content
description: The PFND3DKMT_UNLOCK2 callback function unlocks a list of allocations.
ms.assetid: c6c055d7-5307-4e8f-985e-22dc13aba2e2
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_UNLOCK2
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_UNLOCK2 callback function

## -description

The PFND3DKMT_UNLOCK2 callback function unlocks a list of allocations.

## -prototype

```
//Declaration

PFND3DKMT_UNLOCK2 Pfnd3dkmtUnlock2; 

// Definition

NTSTATUS Pfnd3dkmtUnlock2 
(
	const D3DKMT_UNLOCK2 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_UNLOCK2](ns-d3dkmthk-_d3dkmt_unlock2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also