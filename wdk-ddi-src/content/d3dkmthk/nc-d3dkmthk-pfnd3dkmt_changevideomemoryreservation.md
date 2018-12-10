---
UID: NC:d3dkmthk.PFND3DKMT_CHANGEVIDEOMEMORYRESERVATION
title: PFND3DKMT_CHANGEVIDEOMEMORYRESERVATION
author: windows-driver-content
description: The PFND3DKMT_CHANGEVIDEOMEMORYRESERVATION callback function changes a video memory reservation.
ms.assetid: 2c2dd799-7d1f-4837-8e77-13c3107908ba
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
-	PFND3DKMT_CHANGEVIDEOMEMORYRESERVATION
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_CHANGEVIDEOMEMORYRESERVATION callback function

## -description

The PFND3DKMT_CHANGEVIDEOMEMORYRESERVATION callback function changes a video memory reservation.

## -prototype

```cpp
//Declaration

PFND3DKMT_CHANGEVIDEOMEMORYRESERVATION Pfnd3dkmtChangevideomemoryreservation; 

// Definition

NTSTATUS Pfnd3dkmtChangevideomemoryreservation 
(
	const D3DKMT_CHANGEVIDEOMEMORYRESERVATION *
)
{...}

```

## -parameters

### -param *

Pointer to a [D3DKMT_CHANGEVIDEOMEMORYRESERVATION](ns-d3dkmthk-_d3dkmt_changevideommemoryreservation.md) structure.

## -returns

Returns NTSTATUS.
