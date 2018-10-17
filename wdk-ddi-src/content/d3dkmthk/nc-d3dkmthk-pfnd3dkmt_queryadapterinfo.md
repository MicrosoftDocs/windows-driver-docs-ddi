---
UID: NC:d3dkmthk.PFND3DKMT_QUERYADAPTERINFO
title: PFND3DKMT_QUERYADAPTERINFO
author: windows-driver-content
description: The PFND3DKMT_QUERYADAPTERINFO callback function retrieves graphics adapter information.
ms.assetid: fc4f4324-cb20-49ae-8f1c-3aa8e75d3d9a
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
-	PFND3DKMT_QUERYADAPTERINFO
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_QUERYADAPTERINFO callback function

## -description

The PFND3DKMT_QUERYADAPTERINFO callback function retrieves graphics adapter information.

## -prototype

```
//Declaration

PFND3DKMT_QUERYADAPTERINFO Pfnd3dkmtQueryadapterinfo; 

// Definition

NTSTATUS Pfnd3dkmtQueryadapterinfo 
(
	const D3DKMT_QUERYADAPTERINFO *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_QUERYADAPTERINFO](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
