---
UID: NC:d3dkmthk.PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS
title: PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS (d3dkmthk.h)
description: The PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS callback function sets the scheduling priority for a process.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS callback function"]
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
 - PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS
 - d3dkmthk/PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS
dev_langs:
 - c++
---

# PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS callback function


## -description

The PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS callback function sets the scheduling priority for a process.

## -parameters

### -param Arg1: 

### -param Arg2: 

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS Pfnd3dkmtSetprocessschedulingpriorityclass; 

// Definition

NTSTATUS Pfnd3dkmtSetprocessschedulingpriorityclass 
(
	HANDLE Arg1
	D3DKMT_SCHEDULINGPRIORITYCLASS Arg2
)
{...}

```

## -remarks

## -see-also

