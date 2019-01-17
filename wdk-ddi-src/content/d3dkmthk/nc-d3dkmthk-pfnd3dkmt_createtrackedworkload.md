---
UID: NC:d3dkmthk.PFND3DKMT_CREATETRACKEDWORKLOAD
title: PFND3DKMT_CREATETRACKEDWORKLOAD
description: Creates a tracked workload instance.
ms.assetid: be3bdd91-d69e-4265-acc4-049d6927c432
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
-	PFND3DKMT_CREATETRACKEDWORKLOAD
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3DKMT_CREATETRACKEDWORKLOAD callback function

## -description

Creates a tracked workload instance.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATETRACKEDWORKLOAD Pfnd3dkmtCreatetrackedworkload; 

// Definition

NTSTATUS Pfnd3dkmtCreatetrackedworkload 
(
	D3DKMT_CREATETRACKEDWORKLOAD *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_CREATETRACKEDWORKLOAD](ns-d3dkmthk-_d3dkmt_createtrackedworkload.md) structure to create a tracked workload.

## -returns

Returns NTSTATUS.


## -remarks



## -see-also
