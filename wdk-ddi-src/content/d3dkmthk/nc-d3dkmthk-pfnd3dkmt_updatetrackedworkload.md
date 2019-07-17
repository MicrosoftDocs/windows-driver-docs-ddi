---
UID: NC:d3dkmthk.PFND3DKMT_UPDATETRACKEDWORKLOAD
title: PFND3DKMT_UPDATETRACKEDWORKLOAD (d3dkmthk.h)
description: Updates the tracked workload.
ms.assetid: db657857-c080-4938-8c87-883bc28cd96a
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_UPDATETRACKEDWORKLOAD"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_UPDATETRACKEDWORKLOAD
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3DKMT_UPDATETRACKEDWORKLOAD callback function

## -description

Updates the tracked workload.

## -prototype

```cpp
//Declaration

PFND3DKMT_UPDATETRACKEDWORKLOAD Pfnd3dkmtUpdatetrackedworkload; 

// Definition

NTSTATUS Pfnd3dkmtUpdatetrackedworkload 
(
	D3DKMT_UPDATETRACKEDWORKLOAD *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_UPDATETRACKEDWORKLOAD](ns-d3dkmthk-_d3dkmt_updatetrackedworkload.md) structure.

## -returns

Returns NTSTATUS.

## -remarks



## -see-also
