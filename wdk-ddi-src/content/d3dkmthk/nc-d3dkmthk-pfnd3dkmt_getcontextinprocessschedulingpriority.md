---
UID: NC:d3dkmthk.PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
title: PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY (d3dkmthk.h)
description: The Pfnd3dkmtGetcontextinprocessschedulingpriority callback function is called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.
ms.assetid: e3ddd8ee-6c70-44d6-9312-24b368b22e85
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function"]
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
 - PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
 - d3dkmthk/PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
dev_langs:
 - c++
---

# PFND3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY callback function


## -description

The Pfnd3dkmtGetcontextinprocessschedulingpriority callback function is called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY](ns-d3dkmthk-_d3dkmt_getcontextinprocessschedulingpriority.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

