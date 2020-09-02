---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYDEVICE
title: PFND3DKMT_DESTROYDEVICE (d3dkmthk.h)
description: The PFND3DKMT_DESTROYDEVICE callback function destroys a graphics context device.
ms.assetid: f8c8bc39-b32f-40e7-a707-065fd56210bd
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYDEVICE callback function"]
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
 - PFND3DKMT_DESTROYDEVICE
 - d3dkmthk/PFND3DKMT_DESTROYDEVICE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYDEVICE
dev_langs:
 - c++
---

# PFND3DKMT_DESTROYDEVICE callback function


## -description

The PFND3DKMT_DESTROYDEVICE callback function destroys a graphics context device.

## -parameters

### -param Arg1

A pointer to a [D3DKMT_DESTROYDEVICE](ns-d3dkmthk-_d3dkmt_destroydevice.md) structure.

## -returns

Returns NTSTATUS.

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

