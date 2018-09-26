---
UID: NC:d3dkmthk.PFND3DKMT_OPENKEYEDMUTEX
title: PFND3DKMT_OPENKEYEDMUTEX
author: windows-driver-content
description: Pfnd3dkmtOpenkeyedmutex opens a keyed mutex object that includes private data.
ms.assetid: c5542773-5857-4137-98ac-82467f6e053d
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_OPENKEYEDMUTEX
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_OPENKEYEDMUTEX callback function

## -description

Pfnd3dkmtOpenkeyedmutex opens a keyed mutex object that includes private data.

## -prototype

```
//Declaration

PFND3DKMT_OPENKEYEDMUTEX Pfnd3dkmtOpenkeyedmutex; 

// Definition

NTSTATUS Pfnd3dkmtOpenkeyedmutex 
(
	D3DKMT_OPENKEYEDMUTEX *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENKEYEDMUTEX](ns-d3dkmthk-_d3dkmt_openkeyedmutex.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also