---
UID: NC:d3dkmthk.PFND3DKMT_QUERYALLOCATIONRESIDENCY
title: PFND3DKMT_QUERYALLOCATIONRESIDENCY (d3dkmthk.h)
description: The PFND3DKMT_QUERYALLOCATIONRESIDENCY callback function retrieves the residency status of a resource or list of allocations.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_QUERYALLOCATIONRESIDENCY callback function"]
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
 - PFND3DKMT_QUERYALLOCATIONRESIDENCY
 - d3dkmthk/PFND3DKMT_QUERYALLOCATIONRESIDENCY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_QUERYALLOCATIONRESIDENCY
dev_langs:
 - c++
---

# PFND3DKMT_QUERYALLOCATIONRESIDENCY callback function


## -description

The PFND3DKMT_QUERYALLOCATIONRESIDENCY callback function retrieves the residency status of a resource or list of allocations.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_QUERYALLOCATIONRESIDENCY](ns-d3dkmthk-_d3dkmt_queryallocationresidency.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

