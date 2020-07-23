---
UID: NC:d3dkmthk.PFND3DKMT_PRESENTMULTIPLANEOVERLAY
title: PFND3DKMT_PRESENTMULTIPLANEOVERLAY (d3dkmthk.h)
description: The PFND3DKMT_PRESENTMULTIPLANEOVERLAY callback function copies content from a source multiplane overlay allocation to a destination allocation.
ms.assetid: 2fb551f9-28f3-4bca-8ea4-0f91c2978f0c
ms.date: 10/19/2018
keywords: ["PFND3DKMT_PRESENTMULTIPLANEOVERLAY callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_PRESENTMULTIPLANEOVERLAY"
 - "PFND3DKMT_PRESENTMULTIPLANEOVERLAY"
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
- PFND3DKMT_PRESENTMULTIPLANEOVERLAY
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_PRESENTMULTIPLANEOVERLAY callback function

## -description

The PFND3DKMT_PRESENTMULTIPLANEOVERLAY callback function copies content from a source multiplane overlay allocation to a destination allocation.

## -prototype

```cpp
//Declaration

PFND3DKMT_PRESENTMULTIPLANEOVERLAY Pfnd3dkmtPresentmultiplaneoverlay; 

// Definition

NTSTATUS Pfnd3dkmtPresentmultiplaneoverlay 
(
	const D3DKMT_PRESENT_MULTIPLANE_OVERLAY *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_PRESENT_MULTIPLANE_OVERLAY](ns-d3dkmthk-d3dkmt_present_multiplane_overlay.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
