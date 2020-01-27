---
UID: NC:d3dkmthk.PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS
title: PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS (d3dkmthk.h)
description: The PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS callback function sets the scheduling priority for a process.
ms.assetid: cd229812-8237-46b2-9e13-45248a1e65b7
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS callback function

## -description

The PFND3DKMT_SETPROCESSSCHEDULINGPRIORITYCLASS callback function sets the scheduling priority for a process.

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

## -parameters

### -param Arg1: 
### -param Arg2: 



## -returns

Returns NTSTATUS.


## -remarks




## -see-also
