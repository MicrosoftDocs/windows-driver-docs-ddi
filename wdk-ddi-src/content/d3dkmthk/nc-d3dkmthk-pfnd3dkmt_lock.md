---
UID: NC:d3dkmthk.PFND3DKMT_LOCK
title: PFND3DKMT_LOCK
author: windows-driver-content
description: Pfnd3dkmtLock locks an entire allocation or specific pages within an allocation.
ms.assetid: 64b2e3db-a8f3-44c8-86d8-f7f493475811
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
-	PFND3DKMT_LOCK
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_LOCK callback function

## -description

Pfnd3dkmtLock locks an entire allocation or specific pages within an allocation. 

## -prototype

```cpp
//Declaration

PFND3DKMT_LOCK Pfnd3dkmtLock; 

// Definition

NTSTATUS Pfnd3dkmtLock 
(
	D3DKMT_LOCK *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_LOCK](ns-d3dkmthk-_d3dkmt_lock.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
