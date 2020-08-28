---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYOUTPUTDUPL
title: PFND3DKMT_DESTROYOUTPUTDUPL (d3dkmthk.h)
description: The PFND3DKMT_DESTROYOUTPUTDUPL callback function destroys output duplicates.
ms.assetid: 15c4451d-654d-4e69-b0ed-5d7e3a9b7c2f
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYOUTPUTDUPL callback function"]
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
 - PFND3DKMT_DESTROYOUTPUTDUPL
 - d3dkmthk/PFND3DKMT_DESTROYOUTPUTDUPL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYOUTPUTDUPL
dev_langs:
 - c++
---

# PFND3DKMT_DESTROYOUTPUTDUPL callback function


## -description

The PFND3DKMT_DESTROYOUTPUTDUPL callback function destroys output duplicates.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_DESTROY_OUTPUTDUPL](ns-d3dkmthk-_d3dkmt_destroy_outputdupl.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYOUTPUTDUPL Pfnd3dkmtDestroyoutputdupl; 

// Definition

NTSTATUS Pfnd3dkmtDestroyoutputdupl 
(
	const D3DKMT_DESTROY_OUTPUTDUPL *
)
{...}

```

