---
UID: NC:d3dkmthk.PFND3DKMT_GETSCANLINE
title: PFND3DKMT_GETSCANLINE
author: windows-driver-content
description: Pfnd3dkmtGetscanline determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.
ms.assetid: 05015761-1078-47c8-8e4b-deb02a999e6f
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
-	PFND3DKMT_GETSCANLINE
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_GETSCANLINE callback function

## -description

Pfnd3dkmtGetscanline determines whether the given video present source of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line.

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

## -parameters

### -param * 

Pointer to a [D3DKMT_GETSCANLINE](ns-d3dkmthk-_d3dkmt_getscanline.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
