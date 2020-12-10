---
UID: NC:d3dkmthk.PFND3DKMT_SETVIDPNSOURCEHWPROTECTION
title: PFND3DKMT_SETVIDPNSOURCEHWPROTECTION (d3dkmthk.h)
description: The PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function sets VidPn source hardware protection.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function"]
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
 - PFND3DKMT_SETVIDPNSOURCEHWPROTECTION
 - d3dkmthk/PFND3DKMT_SETVIDPNSOURCEHWPROTECTION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETVIDPNSOURCEHWPROTECTION
dev_langs:
 - c++
---

# PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function


## -description

The PFND3DKMT_SETVIDPNSOURCEHWPROTECTION callback function sets VidPn source hardware protection.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETVIDPNSOURCEHWPROTECTION](ns-d3dkmthk-_d3dkmt_setvidpnsourcehwprotection.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

