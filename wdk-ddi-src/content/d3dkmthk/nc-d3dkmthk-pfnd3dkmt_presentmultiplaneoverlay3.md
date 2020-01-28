---
UID: NC:d3dkmthk.PFND3DKMT_PRESENTMULTIPLANEOVERLAY3
title: PFND3DKMT_PRESENTMULTIPLANEOVERLAY3 (d3dkmthk.h)
description: The PFND3DKMT_PRESENTMULTIPLANEOVERLAY3 callback function copies content from a source multiplane overlay allocation to a destination allocation.
ms.assetid: 6fe0df78-a4ca-4897-b4e9-81489fe19660
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_PRESENTMULTIPLANEOVERLAY3"
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
- PFND3DKMT_PRESENTMULTIPLANEOVERLAY3
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_PRESENTMULTIPLANEOVERLAY3 callback function

## -description

The PFND3DKMT_PRESENTMULTIPLANEOVERLAY3 callback function copies content from a source multiplane overlay allocation to a destination allocation.

## -prototype

```cpp
//Declaration

PFND3DKMT_PRESENTMULTIPLANEOVERLAY3 Pfnd3dkmtPresentmultiplaneoverlay3; 

// Definition

NTSTATUS Pfnd3dkmtPresentmultiplaneoverlay3 
(
	const D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [[D3DKMT_PRESENT_MULTIPLANE_OVERLAY3](ns-d3dkmthk-_d3dkmt_present_multiplane_overlay3.md)]() structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
