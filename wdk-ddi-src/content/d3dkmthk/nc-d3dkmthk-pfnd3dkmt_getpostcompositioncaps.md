---
UID: NC:d3dkmthk.PFND3DKMT_GETPOSTCOMPOSITIONCAPS
title: PFND3DKMT_GETPOSTCOMPOSITIONCAPS
author: windows-driver-content
description: Pfnd3dkmtGetpostcompositioncaps retrieves post composition capabilities.
ms.assetid: 4c14764f-5dfd-4ec2-9185-6aaeca02bafd
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_GETPOSTCOMPOSITIONCAPS
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_GETPOSTCOMPOSITIONCAPS callback function

## -description

Pfnd3dkmtGetpostcompositioncaps retrieves post composition capabilities.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETPOSTCOMPOSITIONCAPS Pfnd3dkmtGetpostcompositioncaps; 

// Definition

NTSTATUS Pfnd3dkmtGetpostcompositioncaps 
(
	D3DKMT_GET_POST_COMPOSITION_CAPS *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GET_POST_COMPOSITION_CAPS](ns-d3dkmthk-_d3dkmt_get_post_composition_caps.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
