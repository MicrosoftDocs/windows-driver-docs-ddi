---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYDEVICE
title: PFND3DKMT_DESTROYDEVICE (d3dkmthk.h)
description: The PFND3DKMT_DESTROYDEVICE callback function destroys a graphics context device.
ms.assetid: f8c8bc39-b32f-40e7-a707-065fd56210bd
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
-	PFND3DKMT_DESTROYDEVICE
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_DESTROYDEVICE callback function

## -description

The PFND3DKMT_DESTROYDEVICE callback function destroys a graphics context device.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYDEVICE Pfnd3dkmtDestroydevice; 

// Definition

NTSTATUS Pfnd3dkmtDestroydevice 
(
	const D3DKMT_DESTROYDEVICE *
)
{...}

```

## -parameters

### -param * 

A pointer to a [D3DKMT_DESTROYDEVICE](ns-d3dkmthk-_d3dkmt_destroydevice.md) structure.

## -returns

Returns NTSTATUS.
