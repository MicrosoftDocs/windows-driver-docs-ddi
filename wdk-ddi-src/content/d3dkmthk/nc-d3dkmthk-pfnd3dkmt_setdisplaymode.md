---
UID: NC:d3dkmthk.PFND3DKMT_SETDISPLAYMODE
title: PFND3DKMT_SETDISPLAYMODE (d3dkmthk.h)
description: The PFND3DKMT_SETDISPLAYMODE callback function sets the allocation that is used to scan out to the display.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETDISPLAYMODE callback function"]
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
 - PFND3DKMT_SETDISPLAYMODE
 - d3dkmthk/PFND3DKMT_SETDISPLAYMODE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETDISPLAYMODE
dev_langs:
 - c++
---

# PFND3DKMT_SETDISPLAYMODE callback function


## -description

The PFND3DKMT_SETDISPLAYMODE callback function sets the allocation that is used to scan out to the display.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETDISPLAYMODE](ns-d3dkmthk-_d3dkmt_setdisplaymode.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETDISPLAYMODE Pfnd3dkmtSetdisplaymode; 

// Definition

NTSTATUS Pfnd3dkmtSetdisplaymode 
(
	const D3DKMT_SETDISPLAYMODE *
)
{...}

```

## -remarks

## -see-also

