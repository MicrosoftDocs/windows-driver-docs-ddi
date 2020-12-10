---
UID: NC:d3dkmthk.PFND3DKMT_GETSCANLINE
title: PFND3DKMT_GETSCANLINE (d3dkmthk.h)
description: Pfnd3dkmtGetscanline determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETSCANLINE callback function"]
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
 - PFND3DKMT_GETSCANLINE
 - d3dkmthk/PFND3DKMT_GETSCANLINE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETSCANLINE
dev_langs:
 - c++
---

# PFND3DKMT_GETSCANLINE callback function


## -description

Pfnd3dkmtGetscanline determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETSCANLINE](ns-d3dkmthk-_d3dkmt_getscanline.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETSCANLINE Pfnd3dkmtGetscanline; 

// Definition

NTSTATUS Pfnd3dkmtGetscanline 
(
	D3DKMT_GETSCANLINE *
)
{...}

```

## -remarks

## -see-also

