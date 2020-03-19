---
UID: NC:d3dkmthk.PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
title: PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY (d3dkmthk.h)
description: The Pfnd3dkmtGetcontextinprocessschedulingpriority callback function is called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.
ms.assetid: e3ddd8ee-6c70-44d6-9312-24b368b22e85
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY"
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
- PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function

## -description

The Pfnd3dkmtGetcontextinprocessschedulingpriority callback function is called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY Pfnd3dkmtGetcontextinprocessschedulingpriority; 

// Definition

NTSTATUS Pfnd3dkmtGetcontextinprocessschedulingpriority 
(
	D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY](ns-d3dkmthk-_d3dkmt_getcontextinprocessschedulingpriority.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
