---
UID: NC:d3dkmthk.PFND3DKMT_PRESENT
title: PFND3DKMT_PRESENT (d3dkmthk.h)
description: The PFND3DKMT_PRESENT callback function submits a present command to the Microsoft DirectX graphics kernel subsystem.
ms.assetid: adf00e57-a1bf-4dec-8043-82ce36ffcb06
ms.date: 10/19/2018
keywords: ["PFND3DKMT_PRESENT callback function"]
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
 - PFND3DKMT_PRESENT
 - d3dkmthk/PFND3DKMT_PRESENT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_PRESENT
dev_langs:
 - c++
---

# PFND3DKMT_PRESENT callback function


## -description

The PFND3DKMT_PRESENT callback function submits a present command to the Microsoft DirectX graphics kernel subsystem.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_PRESENT](ns-d3dkmthk-_d3dkmt_present.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_PRESENT Pfnd3dkmtPresent; 

// Definition

NTSTATUS Pfnd3dkmtPresent 
(
	D3DKMT_PRESENT *
)
{...}

```

## -remarks

## -see-also

