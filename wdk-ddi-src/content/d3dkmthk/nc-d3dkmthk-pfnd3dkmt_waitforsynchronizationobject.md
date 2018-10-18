---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT
title: PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT callback function inserts a wait for the specified synchronization objects in the specified context stream.
ms.assetid: 9e4e8e4e-e326-4571-aee1-ad731b65d53c
ms.date: 
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
-	PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT callback function

## -description

The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT callback function inserts a wait for the specified synchronization objects in the specified context stream.

## -prototype

```cpp
//Declaration

PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECT Pfnd3dkmtWaitforsynchronizationobject; 

// Definition

NTSTATUS Pfnd3dkmtWaitforsynchronizationobject 
(
	D3DKMT_WAITFORSYNCHRONIZATIONOBJECT *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
