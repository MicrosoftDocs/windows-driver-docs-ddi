---
UID: NC:d3dkmthk.PFND3DKMT_QUERYALLOCATIONRESIDENCY
title: PFND3DKMT_QUERYALLOCATIONRESIDENCY
author: windows-driver-content
description: The PFND3DKMT_QUERYALLOCATIONRESIDENCY callback function retrieves the residency status of a resource or list of allocations.
ms.assetid: 3648f3f2-bb95-44af-9dc1-ee169cc03dfc
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
-	PFND3DKMT_QUERYALLOCATIONRESIDENCY
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_QUERYALLOCATIONRESIDENCY callback function

## -description

The PFND3DKMT_QUERYALLOCATIONRESIDENCY callback function retrieves the residency status of a resource or list of allocations.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYALLOCATIONRESIDENCY Pfnd3dkmtQueryallocationresidency; 

// Definition

NTSTATUS Pfnd3dkmtQueryallocationresidency 
(
	const D3DKMT_QUERYALLOCATIONRESIDENCY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_QUERYALLOCATIONRESIDENCY](ns-d3dkmthk-_d3dkmt_queryallocationresidency.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
