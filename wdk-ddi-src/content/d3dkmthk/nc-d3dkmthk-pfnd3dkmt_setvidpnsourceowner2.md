---
UID: NC:d3dkmthk.PFND3DKMT_SETVIDPNSOURCEOWNER2
title: PFND3DKMT_SETVIDPNSOURCEOWNER2 (d3dkmthk.h)
description: The PFND3DKMT_SETVIDPNSOURCEOWNER2 callback function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
ms.assetid: e9401358-5658-4145-b609-82743f3a5e2b
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETVIDPNSOURCEOWNER2 callback function"]
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
 - PFND3DKMT_SETVIDPNSOURCEOWNER2
 - d3dkmthk/PFND3DKMT_SETVIDPNSOURCEOWNER2
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SETVIDPNSOURCEOWNER2
dev_langs:
 - c++
---

# PFND3DKMT_SETVIDPNSOURCEOWNER2 callback function


## -description

The PFND3DKMT_SETVIDPNSOURCEOWNER2 callback function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SETVIDPNSOURCEOWNER2](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner2.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETVIDPNSOURCEOWNER2 Pfnd3dkmtSetvidpnsourceowner2; 

// Definition

NTSTATUS Pfnd3dkmtSetvidpnsourceowner2 
(
	const D3DKMT_SETVIDPNSOURCEOWNER2 *
)
{...}

```

## -remarks

## -see-also

