---
UID: NC:d3dkmthk.PFND3DKMT_UPDATEOVERLAY
title: PFND3DKMT_UPDATEOVERLAY (d3dkmthk.h)
description: PFND3DKMT_UPDATEOVERLAY callback function modifies a kernel-mode overlay object.
ms.assetid: 05fd48da-c107-4964-a042-e2662ac70828
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UPDATEOVERLAY callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_UPDATEOVERLAY"
 - "PFND3DKMT_UPDATEOVERLAY"
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
- PFND3DKMT_UPDATEOVERLAY
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_UPDATEOVERLAY callback function

## -description

PFND3DKMT_UPDATEOVERLAY callback function modifies a kernel-mode overlay object.

## -prototype

```cpp
//Declaration

PFND3DKMT_UPDATEOVERLAY Pfnd3dkmtUpdateoverlay; 

// Definition

NTSTATUS Pfnd3dkmtUpdateoverlay 
(
	const D3DKMT_UPDATEOVERLAY *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_UPDATEOVERLAY](ns-d3dkmthk-_d3dkmt_updateoverlay.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
