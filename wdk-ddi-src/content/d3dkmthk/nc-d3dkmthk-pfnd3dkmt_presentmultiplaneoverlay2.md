---
UID: NC:d3dkmthk.PFND3DKMT_PRESENTMULTIPLANEOVERLAY2
title: PFND3DKMT_PRESENTMULTIPLANEOVERLAY2 (d3dkmthk.h)
description: The PFND3DKMT_PRESENTMULTIPLANEOVERLAY2 callback function copies content from a source multiplane overlay allocation to a destination allocation.
ms.assetid: a5465ec7-d6c0-49de-984e-28d263cc96d8
ms.date: 10/19/2018
keywords: ["PFND3DKMT_PRESENTMULTIPLANEOVERLAY2 callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_PRESENTMULTIPLANEOVERLAY2"
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
- PFND3DKMT_PRESENTMULTIPLANEOVERLAY2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_PRESENTMULTIPLANEOVERLAY2 callback function

## -description

The PFND3DKMT_PRESENTMULTIPLANEOVERLAY2 callback function copies content from a source multiplane overlay allocation to a destination allocation.

## -prototype

```cpp
//Declaration

PFND3DKMT_PRESENTMULTIPLANEOVERLAY2 Pfnd3dkmtPresentmultiplaneoverlay2; 

// Definition

NTSTATUS Pfnd3dkmtPresentmultiplaneoverlay2 
(
	const D3DKMT_PRESENT_MULTIPLANE_OVERLAY2 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_PRESENT_MULTIPLANE_OVERLAY2](ns-d3dkmthk-_d3dkmt_present_multiplane_overlay2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
