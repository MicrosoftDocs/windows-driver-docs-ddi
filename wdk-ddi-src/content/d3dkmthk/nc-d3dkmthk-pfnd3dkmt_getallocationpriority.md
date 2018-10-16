---
UID: NC:d3dkmthk.PFND3DKMT_GETALLOCATIONPRIORITY
title: PFND3DKMT_GETALLOCATIONPRIORITY
author: windows-driver-content
description: The Pfnd3dkmtGetallocationpriority callback function gets allocation priority.
ms.assetid: 896340a0-408c-41ec-81e2-f720f10e20d7
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
-	PFND3DKMT_GETALLOCATIONPRIORITY
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_GETALLOCATIONPRIORITY callback function

## -description

The Pfnd3dkmtGetallocationpriority callback function gets allocation priority.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETALLOCATIONPRIORITY Pfnd3dkmtGetallocationpriority; 

// Definition

NTSTATUS Pfnd3dkmtGetallocationpriority 
(
	const D3DKMT_GETALLOCATIONPRIORITY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETALLOCATIONPRIORITY](ns-d3dkmthk-_d3dkmt_getallocationpriority.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
