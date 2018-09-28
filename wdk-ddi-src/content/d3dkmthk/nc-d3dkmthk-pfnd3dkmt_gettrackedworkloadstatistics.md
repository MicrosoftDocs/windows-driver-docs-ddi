---
UID: NC:d3dkmthk.PFND3DKMT_GETTRACKEDWORKLOADSTATISTICS
title: PFND3DKMT_GETTRACKEDWORKLOADSTATISTICS
author: windows-driver-content
description: Retrieves the rolling statistics for the tracked workload.
ms.assetid: d0f745bc-f54b-4f16-8f43-eb435c51d7cc
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
-	PFND3DKMT_GETTRACKEDWORKLOADSTATISTICS
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3DKMT_GETTRACKEDWORKLOADSTATISTICS callback function

## -description

Retrieves the rolling statistics for the tracked workload.

Note that it just returns stats for work that is currently completed.

## -prototype

```
//Declaration

PFND3DKMT_GETTRACKEDWORKLOADSTATISTICS Pfnd3dkmtGettrackedworkloadstatistics; 

// Definition

NTSTATUS Pfnd3dkmtGettrackedworkloadstatistics 
(
	D3DKMT_GETTRACKEDWORKLOADSTATISTICS *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETTRACKEDWORKLOADSTATISTICS](ns-d3dkmthk-_d3dkmt_gettrackedworkloadstatistics.md) structure to get the tracked workload statistics.

## -returns

Returns NTSTATUS that.

## -remarks



## -see-also