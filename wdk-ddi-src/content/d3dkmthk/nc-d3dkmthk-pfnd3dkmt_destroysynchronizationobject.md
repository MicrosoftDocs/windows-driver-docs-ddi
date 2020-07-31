---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT
title: PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT callback function destroys synchronization object.
ms.assetid: 78c47d52-a3aa-4541-9b65-51dbf5a14f11
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT"
 - "PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT"
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
- PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT callback function

## -description

The PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT callback function destroys synchronization object.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT Pfnd3dkmtDestroysynchronizationobject; 

// Definition

NTSTATUS Pfnd3dkmtDestroysynchronizationobject 
(
	const D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_DESTROYSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_destroysynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.
