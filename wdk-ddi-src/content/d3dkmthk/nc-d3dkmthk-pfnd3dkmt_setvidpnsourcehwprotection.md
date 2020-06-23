---
UID: NC:d3dkmthk.PFND3DKMT_SETVIDPNSOURCEHWPROTECTION
title: PFND3DKMT_SETVIDPNSOURCEHWPROTECTION (d3dkmthk.h)
description: The PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function sets VidPn source hardware protection.
ms.assetid: 344b5493-91fd-4c43-b8ba-ee7d918cb9c6
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETVIDPNSOURCEHWPROTECTION"
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
- PFND3DKMT_SETVIDPNSOURCEHWPROTECTION
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function

## -description

The PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function sets VidPn source hardware protection.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETVIDPNSOURCEHWPROTECTION Pfnd3dkmtSetvidpnsourcehwprotection; 

// Definition

NTSTATUS Pfnd3dkmtSetvidpnsourcehwprotection 
(
	D3DKMT_SETVIDPNSOURCEHWPROTECTION *
)
{...}

```

## -parameters

### -param  

Pointer to a [D3DKMT_SETVIDPNSOURCEHWPROTECTION](ns-d3dkmthk-_d3dkmt_setvidpnsourcehwprotection.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
