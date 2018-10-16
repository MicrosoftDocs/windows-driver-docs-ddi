---
UID: NC:d3dkmthk.PFND3DKMT_UNLOCK
title: PFND3DKMT_UNLOCK
author: windows-driver-content
description: The PFND3DKMT_UNLOCK callback function unlocks a list of allocations.
ms.assetid: c64b363e-13bd-4bd9-8752-70395c124226
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
-	PFND3DKMT_UNLOCK
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_UNLOCK callback function

## -description

The PFND3DKMT_UNLOCK callback function unlocks a list of allocations.

## -prototype

```cpp
//Declaration

PFND3DKMT_UNLOCK Pfnd3dkmtUnlock; 

// Definition

NTSTATUS Pfnd3dkmtUnlock 
(
	const D3DKMT_UNLOCK *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_UNLOCK](ns-d3dkmthk-_d3dkmt_unlock.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
