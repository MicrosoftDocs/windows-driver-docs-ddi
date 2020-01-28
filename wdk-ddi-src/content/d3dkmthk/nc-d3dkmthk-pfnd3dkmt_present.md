---
UID: NC:d3dkmthk.PFND3DKMT_PRESENT
title: PFND3DKMT_PRESENT (d3dkmthk.h)
description: The PFND3DKMT_PRESENT callback function submits a present command to the Microsoft DirectX graphics kernel subsystem.
ms.assetid: adf00e57-a1bf-4dec-8043-82ce36ffcb06
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_PRESENT"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_PRESENT
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_PRESENT callback function

## -description

The PFND3DKMT_PRESENT callback function submits a present command to the Microsoft DirectX graphics kernel subsystem. 

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

## -parameters

### -param * 

Pointer to a [D3DKMT_PRESENT](ns-d3dkmthk-_d3dkmt_present.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
