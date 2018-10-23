---
UID: NC:d3dkmthk.PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
title: PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
author: windows-driver-content
description: Pfnd3dkmtGetprocessschedulingpriorityclass retrieves the scheduling priority for a process.
ms.assetid: 40923029-966b-4782-9d13-f647ddbc6ec0
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
-	PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS callback function

## -description

Pfnd3dkmtGetprocessschedulingpriorityclass retrieves the scheduling priority for a process.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS Pfnd3dkmtGetprocessschedulingpriorityclass; 

// Definition

NTSTATUS Pfnd3dkmtGetprocessschedulingpriorityclass 
(
	HANDLE Arg1
	D3DKMT_SCHEDULINGPRIORITYCLASS *
)
{...}

```

## -parameters

### -param Arg1

A handle to a display device.

### -param * 

Pointer to a D3DKMT_SCHEDULINGPRIORITYCLASS structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
