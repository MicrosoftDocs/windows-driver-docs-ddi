---
UID: NC:d3dkmthk.PFND3DKMT_QUERYVIDEOMEMORYINFO
title: PFND3DKMT_QUERYVIDEOMEMORYINFO (d3dkmthk.h)
description: The PFND3DKMT_QUERYVIDEOMEMORYINFO callback function queries for video memory info.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_QUERYVIDEOMEMORYINFO callback function"]
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
 - PFND3DKMT_QUERYVIDEOMEMORYINFO
 - d3dkmthk/PFND3DKMT_QUERYVIDEOMEMORYINFO
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_QUERYVIDEOMEMORYINFO
dev_langs:
 - c++
---

# PFND3DKMT_QUERYVIDEOMEMORYINFO callback function


## -description

The PFND3DKMT_QUERYVIDEOMEMORYINFO callback function queries for video memory info.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_QUERYVIDEOMEMORYINFO](ns-d3dkmthk-_d3dkmt_queryvideomemoryinfo.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYVIDEOMEMORYINFO Pfnd3dkmtQueryvideomemoryinfo; 

// Definition

NTSTATUS Pfnd3dkmtQueryvideomemoryinfo 
(
	D3DKMT_QUERYVIDEOMEMORYINFO *
)
{...}

```

## -remarks

## -see-also

