---
UID: NC:d3dkmthk.PFND3DKMT_CREATESYNCHRONIZATIONOBJECT
title: PFND3DKMT_CREATESYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The PFND3DKMT_CREATESYNCHRONIZATIONOBJECT callback function creates a synchronization object.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATESYNCHRONIZATIONOBJECT callback function"]
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
 - PFND3DKMT_CREATESYNCHRONIZATIONOBJECT
 - d3dkmthk/PFND3DKMT_CREATESYNCHRONIZATIONOBJECT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATESYNCHRONIZATIONOBJECT
dev_langs:
 - c++
---

# PFND3DKMT_CREATESYNCHRONIZATIONOBJECT callback function


## -description

The PFND3DKMT_CREATESYNCHRONIZATIONOBJECT callback function creates a synchronization object.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_CREATESYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_createsynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATESYNCHRONIZATIONOBJECT Pfnd3dkmtCreatesynchronizationobject; 

// Definition

NTSTATUS Pfnd3dkmtCreatesynchronizationobject 
(
	D3DKMT_CREATESYNCHRONIZATIONOBJECT *
)
{...}

```

