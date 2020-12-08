---
UID: NC:d3dkmthk.PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
title: PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS (d3dkmthk.h)
description: Pfnd3dkmtGetprocessschedulingpriorityclass retrieves the scheduling priority for a process.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
 - d3dkmthk/PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
dev_langs:
 - c++
---

# PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS callback function


## -description

Pfnd3dkmtGetprocessschedulingpriorityclass retrieves the scheduling priority for a process.

## -parameters

### -param Arg1

A handle to a display device.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

