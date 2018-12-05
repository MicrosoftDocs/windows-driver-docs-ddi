---
UID: NC:d3dkmthk.PFND3DKMT_RECLAIMALLOCATIONS2
title: PFND3DKMT_RECLAIMALLOCATIONS2
author: windows-driver-content
description: The PFND3DKMT_RECLAIMALLOCATIONS2 callback function reclaims video memory allocations.
ms.assetid: 0acb809e-a536-4422-b216-971cd4b3b57f
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
-	PFND3DKMT_RECLAIMALLOCATIONS2
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_RECLAIMALLOCATIONS2 callback function

## -description

The PFND3DKMT_RECLAIMALLOCATIONS2 callback function reclaims video memory allocations. 

## -prototype

```cpp
//Declaration

PFND3DKMT_RECLAIMALLOCATIONS2 Pfnd3dkmtReclaimallocations2; 

// Definition

NTSTATUS Pfnd3dkmtReclaimallocations2 
(
	D3DKMT_RECLAIMALLOCATIONS2 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_RECLAIMALLOCATIONS2](ns-d3dkmthk-_d3dkmt_reclaimallocations2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
