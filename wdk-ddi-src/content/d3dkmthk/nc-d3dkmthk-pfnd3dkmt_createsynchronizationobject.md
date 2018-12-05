---
UID: NC:d3dkmthk.PFND3DKMT_CREATESYNCHRONIZATIONOBJECT
title: PFND3DKMT_CREATESYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The PFND3DKMT_CREATESYNCHRONIZATIONOBJECT callback function creates a synchronization object.
ms.assetid: 5f43b3fc-6542-45bf-b169-ab5e4bf2c0f8
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
-	PFND3DKMT_CREATESYNCHRONIZATIONOBJECT
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_CREATESYNCHRONIZATIONOBJECT callback function

## -description

The PFND3DKMT_CREATESYNCHRONIZATIONOBJECT callback function creates a synchronization object.

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

## -parameters

### -param * 

Pointer to a [D3DKMT_CREATESYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_createsynchronizationobject.md) structure.

## -returns

Returns NTSTATUS.
