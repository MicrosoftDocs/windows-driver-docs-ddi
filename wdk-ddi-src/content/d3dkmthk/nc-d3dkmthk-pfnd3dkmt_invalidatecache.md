---
UID: NC:d3dkmthk.PFND3DKMT_INVALIDATECACHE
title: PFND3DKMT_INVALIDATECACHE
author: windows-driver-content
description: Pfnd3dkmtInvalidatecache invalidates cache.
ms.assetid: ce64469b-aff9-44d2-9c6f-a9f5affe6412
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
-	PFND3DKMT_INVALIDATECACHE
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_INVALIDATECACHE callback function

## -description

Pfnd3dkmtInvalidatecache invalidates cache.

## -prototype

```
//Declaration

PFND3DKMT_INVALIDATECACHE Pfnd3dkmtInvalidatecache; 

// Definition

NTSTATUS Pfnd3dkmtInvalidatecache 
(
	const D3DKMT_INVALIDATECACHE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_INVALIDATECACHE](ns-d3dkmthk-_d3dkmt_invalidatecache.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also