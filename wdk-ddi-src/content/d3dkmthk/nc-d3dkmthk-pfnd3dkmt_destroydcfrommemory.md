---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYDCFROMMEMORY
title: PFND3DKMT_DESTROYDCFROMMEMORY
author: windows-driver-content
description: The PFND3DKMT_DESTROYDCFROMMEMORY callback function destroys a device context from memory.
ms.assetid: bd569dac-e7ff-4782-833a-227eb7ccdd82
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
-	PFND3DKMT_DESTROYDCFROMMEMORY
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_DESTROYDCFROMMEMORY callback function

## -description

The PFND3DKMT_DESTROYDCFROMMEMORY callback function destroys a device context from memory.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYDCFROMMEMORY Pfnd3dkmtDestroydcfrommemory; 

// Definition

NTSTATUS Pfnd3dkmtDestroydcfrommemory 
(
	const D3DKMT_DESTROYDCFROMMEMORY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_DESTROYDCFROMMEMORY](ns-d3dkmthk-_d3dkmt_destroydcfrommemory.md) structure.

## -returns

Returns NTSTATUS.
