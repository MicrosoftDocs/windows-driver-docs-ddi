---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITCOMMAND
title: PFND3DKMT_SUBMITCOMMAND (d3dkmthk.h)
description: The PFND3DKMT_SUBMITCOMMAND callback function is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SUBMITCOMMAND callback function"]
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
 - PFND3DKMT_SUBMITCOMMAND
 - d3dkmthk/PFND3DKMT_SUBMITCOMMAND
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_SUBMITCOMMAND
dev_langs:
 - c++
---

# PFND3DKMT_SUBMITCOMMAND callback function


## -description

The PFND3DKMT_SUBMITCOMMAND callback function is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_SUBMITCOMMAND](ns-d3dkmthk-_d3dkmt_submitcommand.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_SUBMITCOMMAND Pfnd3dkmtSubmitcommand; 

// Definition

NTSTATUS Pfnd3dkmtSubmitcommand 
(
	const D3DKMT_SUBMITCOMMAND *
)
{...}

```

## -remarks

## -see-also

