---
UID: NC:d3dkmthk.PFND3DKMT_FLIPOVERLAY
title: PFND3DKMT_FLIPOVERLAY (d3dkmthk.h)
description: The Pfnd3dkmtFlipoverlay callback function displays a new allocation by using the specified overlay.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_FLIPOVERLAY callback function"]
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
 - PFND3DKMT_FLIPOVERLAY
 - d3dkmthk/PFND3DKMT_FLIPOVERLAY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_FLIPOVERLAY
dev_langs:
 - c++
---

# PFND3DKMT_FLIPOVERLAY callback function


## -description

The Pfnd3dkmtFlipoverlay callback function displays a new allocation by using the specified overlay.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_FLIPOVERLAY](ns-d3dkmthk-_d3dkmt_flipoverlay.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_FLIPOVERLAY Pfnd3dkmtFlipoverlay; 

// Definition

NTSTATUS Pfnd3dkmtFlipoverlay 
(
	const D3DKMT_FLIPOVERLAY *
)
{...}

```

## -remarks

## -see-also

