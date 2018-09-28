---
UID: NC:d3dkmthk.PFND3DKMT_QUERYHYBRIDLISTVALUE
title: PFND3DKMT_QUERYHYBRIDLISTVALUE
author: windows-driver-content
description: The PFND3DKMT_QUERYHYBRIDLISTVALUE callback function queries for the hybrid list value.
ms.assetid: ccfe5778-0d18-4196-b840-2f53d9ed36a8
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_QUERYHYBRIDLISTVALUE
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_QUERYHYBRIDLISTVALUE callback function

## -description

The PFND3DKMT_QUERYHYBRIDLISTVALUE callback function queries for the hybrid list value.

## -prototype

```
//Declaration

PFND3DKMT_QUERYHYBRIDLISTVALUE Pfnd3dkmtQueryhybridlistvalue; 

// Definition

NTSTATUS Pfnd3dkmtQueryhybridlistvalue 
(
	D3DKMT_HYBRID_LIST *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_HYBRID_LIST](ns-d3dkmthk-_d3dkmt_hybrid_list.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also