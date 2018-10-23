---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYALLOCATION2
title: PFND3DKMT_DESTROYALLOCATION2
author: windows-driver-content
description: The PFND3DKMT_DESTROYALLOCATION2 callback function releases allocations.
ms.assetid: 184d35d6-4d28-4153-a9a1-d5ccd04827cd
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
-	PFND3DKMT_DESTROYALLOCATION2
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_DESTROYALLOCATION2 callback function

## -description

The PFND3DKMT_DESTROYALLOCATION2 callback function releases allocations.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYALLOCATION2 Pfnd3dkmtDestroyallocation2; 

// Definition

NTSTATUS Pfnd3dkmtDestroyallocation2 
(
	const D3DKMT_DESTROYALLOCATION2 *
)
{...}

```

## -parameters

### -param *

Pointer to a [D3DKMT_DESTROYALLOCATION2](ns-d3dkmthk-_d3dkmt_destroyallocation2.md) structure.

## -returns

Returns NTSTATUS.
