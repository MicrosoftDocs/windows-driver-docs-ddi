---
UID: NC:d3dkmthk.PFND3DKMT_QUERYFSEBLOCK
title: PFND3DKMT_QUERYFSEBLOCK (d3dkmthk.h)
description: The PFND3DKMT_QUERYFSEBLOCK callback function queries FSE blocks.
ms.assetid: 699577c3-0e0d-4518-88e7-40a6992a41ce
ms.date: 10/19/2018
keywords: ["PFND3DKMT_QUERYFSEBLOCK callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_QUERYFSEBLOCK"
 - "PFND3DKMT_QUERYFSEBLOCK"
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
- PFND3DKMT_QUERYFSEBLOCK
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_QUERYFSEBLOCK callback function

## -description

The PFND3DKMT_QUERYFSEBLOCK callback function queries FSE blocks.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYFSEBLOCK Pfnd3dkmtQueryfseblock; 

// Definition

NTSTATUS Pfnd3dkmtQueryfseblock 
(
	D3DKMT_QUERYFSEBLOCK *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_QUERYFSEBLOCK](ns-d3dkmthk-_d3dkmt_queryfseblock.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
