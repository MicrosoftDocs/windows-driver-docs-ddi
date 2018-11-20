---
UID: NC:d3dkmthk.PFND3DKMT_RESETTRACKEDWORKLOAD
title: PFND3DKMT_RESETTRACKEDWORKLOAD
author: windows-driver-content
description: Resets the tracked workload to its initial state and resets all the rolling statistics.
ms.assetid: 1c932978-e7b5-4b29-b08f-3ad2d91cbcf1
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
-	PFND3DKMT_RESETTRACKEDWORKLOAD
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3DKMT_RESETTRACKEDWORKLOAD callback function

## -description

Resets the tracked workload to its initial state and resets all the rolling statistics.

Note that it will reset all previously tracked workloads, and current work in flight in the GPU will affect upcoming stats.

## -prototype

```cpp
//Declaration

PFND3DKMT_RESETTRACKEDWORKLOAD Pfnd3dkmtResettrackedworkload; 

// Definition

NTSTATUS Pfnd3dkmtResettrackedworkload 
(
	D3DKMT_RESETTRACKEDWORKLOAD *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_RESETTRACKEDWORKLOAD](ns-d3dkmthk-_d3dkmt_resettrackedworkload.md) structure to reset the tracked workload.

## -returns

Returns NTSTATUS that.

## -remarks


## -see-also
