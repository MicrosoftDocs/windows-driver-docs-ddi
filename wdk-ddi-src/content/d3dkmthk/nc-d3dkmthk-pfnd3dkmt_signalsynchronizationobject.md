---
UID: NC:d3dkmthk.PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT
title: PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT callback function inserts a signal for the specified synchronization objects in the specified context stream.
ms.assetid: 2e5592f8-96bc-4ec8-961a-38fc2dbc9dfe
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT"
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
- PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT callback function

## -description

The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT callback function inserts a signal for the specified synchronization objects in the specified context stream.

## -prototype

```cpp
//Declaration

PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT Pfnd3dkmtSignalsynchronizationobject; 

// Definition

NTSTATUS Pfnd3dkmtSignalsynchronizationobject 
(
	const D3DKMT_SIGNALSYNCHRONIZATIONOBJECT *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SIGNALSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_signalsynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
