---
UID: NC:d3dkmthk.PFND3DKMT_GETMULTIPLANEOVERLAYCAPS
title: PFND3DKMT_GETMULTIPLANEOVERLAYCAPS
description: Pfnd3dkmtGetmultiplaneoverlaycaps retrieves multiplane overlay capabilities.
ms.assetid: 1c060cf5-6129-4fd2-8bf9-74e4ceb037b6
ms.date: 10/19/2018
ms.topic: callback
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_GETMULTIPLANEOVERLAYCAPS
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_GETMULTIPLANEOVERLAYCAPS callback function

## -description

Pfnd3dkmtGetmultiplaneoverlaycaps retrieves multiplane overlay capabilities.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETMULTIPLANEOVERLAYCAPS Pfnd3dkmtGetmultiplaneoverlaycaps; 

// Definition

NTSTATUS Pfnd3dkmtGetmultiplaneoverlaycaps 
(
	D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GET_MULTIPLANE_OVERLAY_CAPS](ns-d3dkmthk-_d3dkmt_get_multiplane_overlay_caps.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
