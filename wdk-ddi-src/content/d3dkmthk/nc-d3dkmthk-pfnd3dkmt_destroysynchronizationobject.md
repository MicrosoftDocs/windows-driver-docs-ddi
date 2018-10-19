---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT
title: PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT callback function destroys synchronization object.
ms.assetid: 78c47d52-a3aa-4541-9b65-51dbf5a14f11
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
-	PFND3DKMT_DESTROYSYNCHRONIZATIONOBJECT
product:
-	Windows
targetos: Windows
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

### -param * 

Pointer to a [D3DKMT_DESTROYSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_destroysynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.
