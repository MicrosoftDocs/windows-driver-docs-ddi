---
UID: NC:d3dkmthk.PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT
title: PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT callback function inserts a signal for the specified synchronization objects in the specified context stream.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT callback function"]
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
 - PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT
 - d3dkmthk/PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT
dev_langs:
 - c++
---

# PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT callback function


## -description

The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECT callback function inserts a signal for the specified synchronization objects in the specified context stream.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SIGNALSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_signalsynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

