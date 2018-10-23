---
UID: NC:d3dkmthk.PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
title: PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
author: windows-driver-content
description: The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 callback function inserts a signal for the specified synchronization objects in the specified context stream.
ms.assetid: 95443162-df68-4190-9c0a-6dc226526469
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
-	PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT2
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 callback function

## -description

The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 callback function inserts a signal for the specified synchronization objects in the specified context stream.

## -prototype

```cpp
//Declaration

PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 Pfnd3dkmtSignalsynchronizationobject2; 

// Definition

NTSTATUS Pfnd3dkmtSignalsynchronizationobject2 
(
	const D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2](ns-d3dkmthk-_d3dkmt_signalsynchronizationobject2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
