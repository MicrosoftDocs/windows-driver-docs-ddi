---
UID: NC:d3dkmthk.PFND3DKMT_GETSHAREDPRIMARYHANDLE
title: PFND3DKMT_GETSHAREDPRIMARYHANDLE (d3dkmthk.h)
description: Pfnd3dkmtGetsharedprimaryhandle retrieves the global shared handle for the primary surface.
ms.assetid: 264423b0-f635-4530-a0e8-c9ac3dac9e4c
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETSHAREDPRIMARYHANDLE callback function"]
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
 - PFND3DKMT_GETSHAREDPRIMARYHANDLE
 - d3dkmthk/PFND3DKMT_GETSHAREDPRIMARYHANDLE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETSHAREDPRIMARYHANDLE
dev_langs:
 - c++
---

# PFND3DKMT_GETSHAREDPRIMARYHANDLE callback function


## -description

Pfnd3dkmtGetsharedprimaryhandle retrieves the global shared handle for the primary surface.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETSHAREDPRIMARYHANDLE](ns-d3dkmthk-_d3dkmt_getsharedprimaryhandle.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETSHAREDPRIMARYHANDLE Pfnd3dkmtGetsharedprimaryhandle; 

// Definition

NTSTATUS Pfnd3dkmtGetsharedprimaryhandle 
(
	D3DKMT_GETSHAREDPRIMARYHANDLE *
)
{...}

```

## -remarks

## -see-also

