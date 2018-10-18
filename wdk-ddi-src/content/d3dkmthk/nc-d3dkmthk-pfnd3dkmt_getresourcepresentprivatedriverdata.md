---
UID: NC:d3dkmthk.PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA
title: PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA
author: windows-driver-content
description: Pfnd3dkmtGetresourcepresentprivatedriverdata queries the resource private data, which is associated with the resource during Present.
ms.assetid: 598b2722-a60f-4f26-9e65-ba015b2ffa51
ms.date: 
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
-	PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA callback function

## -description

Pfnd3dkmtGetresourcepresentprivatedriverdata queries the resource private data, which is associated with the resource during Present.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETRESOURCEPRESENTPRIVATEDRIVERDATA Pfnd3dkmtGetresourcepresentprivatedriverdata; 

// Definition

NTSTATUS Pfnd3dkmtGetresourcepresentprivatedriverdata 
(
	D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA](../d3dukmdt/ns-d3dukmdt-_d3dddi_getresourcepresentprivatedriverdata.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
