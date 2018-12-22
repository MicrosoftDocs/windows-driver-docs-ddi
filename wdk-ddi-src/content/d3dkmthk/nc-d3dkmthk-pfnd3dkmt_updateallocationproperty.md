---
UID: NC:d3dkmthk.PFND3DKMT_UPDATEALLOCATIONPROPERTY
title: PFND3DKMT_UPDATEALLOCATIONPROPERTY
description: The PFND3DKMT_UPDATEALLOCATIONPROPERTY callback function updates allocation property of a context.
ms.assetid: 70da6f66-26d7-47c6-8236-2003cfa6edf3
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
-	PFND3DKMT_UPDATEALLOCATIONPROPERTY
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_UPDATEALLOCATIONPROPERTY callback function

## -description

The PFND3DKMT_UPDATEALLOCATIONPROPERTY callback function updates allocation property of a context.

## -prototype

```cpp
//Declaration

PFND3DKMT_UPDATEALLOCATIONPROPERTY Pfnd3dkmtUpdateallocationproperty; 

// Definition

NTSTATUS Pfnd3dkmtUpdateallocationproperty 
(
	D3DDDI_UPDATEALLOCPROPERTY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DDDI_UPDATEALLOCPROPERTY](../d3dukmdt/ns-d3dukmdt-d3dddi_updateallocproperty.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
