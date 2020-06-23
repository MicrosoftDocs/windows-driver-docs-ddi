---
UID: NC:d3dkmthk.PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2
title: PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2 (d3dkmthk.h)
description: The PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2 callback function creates a synchronization object.
ms.assetid: 5fff0987-f4dd-4a6e-9415-0e9bf5be4d00
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2 callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2"
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
- PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2 callback function

## -description

The PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2 callback function creates a synchronization object.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATESYNCHRONIZATIONOBJECT2 Pfnd3dkmtCreatesynchronizationobject2; 

// Definition

NTSTATUS Pfnd3dkmtCreatesynchronizationobject2 
(
	D3DKMT_CREATESYNCHRONIZATIONOBJECT2 *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_CREATESYNCHRONIZATIONOBJECT2](ns-d3dkmthk-_d3dkmt_createsynchronizationobject2.md) structure.

## -returns

Returns NTSTATUS.
