---
UID: NC:d3dkmthk.PFND3DKMT_SETVIDPNSOURCEOWNER
title: PFND3DKMT_SETVIDPNSOURCEOWNER (d3dkmthk.h)
description: The PFND3DKMT_SETVIDPNSOURCEOWNER callback function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETVIDPNSOURCEOWNER callback function"]
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
 - PFND3DKMT_SETVIDPNSOURCEOWNER
 - d3dkmthk/PFND3DKMT_SETVIDPNSOURCEOWNER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETVIDPNSOURCEOWNER
dev_langs:
 - c++
---

# PFND3DKMT_SETVIDPNSOURCEOWNER callback function


## -description

The PFND3DKMT_SETVIDPNSOURCEOWNER callback function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETVIDPNSOURCEOWNER Pfnd3dkmtSetvidpnsourceowner; 

// Definition

NTSTATUS Pfnd3dkmtSetvidpnsourceowner 
(
	const D3DKMT_SETVIDPNSOURCEOWNER *
)
{...}

```

## -remarks

## -see-also

