---
UID: NC:d3dkmthk.PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
title: PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION (d3dkmthk.h)
description: The PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION callback function notifies the operating system about an upcoming lock to a shared primary surface.
ms.assetid: ceb858a0-a82b-4649-9a97-884cdf09b822
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION"
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
- PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION callback function

## -description

The PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION callback function notifies the operating system about an upcoming lock to a shared primary surface.

## -prototype

```cpp
//Declaration

PFND3DKMT_SHAREDPRIMARYLOCKNOTIFICATION Pfnd3dkmtSharedprimarylocknotification; 

// Definition

NTSTATUS Pfnd3dkmtSharedprimarylocknotification 
(
	const D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION](ns-d3dkmthk-_d3dkmt_sharedprimarylocknotification.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
