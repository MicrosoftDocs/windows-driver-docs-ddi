---
UID: NC:d3dkmthk.PFND3DKMT_UPDATEALLOCATIONPROPERTY
title: PFND3DKMT_UPDATEALLOCATIONPROPERTY (d3dkmthk.h)
description: The PFND3DKMT_UPDATEALLOCATIONPROPERTY callback function updates allocation property of a context.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UPDATEALLOCATIONPROPERTY callback function"]
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
 - PFND3DKMT_UPDATEALLOCATIONPROPERTY
 - d3dkmthk/PFND3DKMT_UPDATEALLOCATIONPROPERTY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_UPDATEALLOCATIONPROPERTY
dev_langs:
 - c++
---

# PFND3DKMT_UPDATEALLOCATIONPROPERTY callback function


## -description

The PFND3DKMT_UPDATEALLOCATIONPROPERTY callback function updates allocation property of a context.

## -parameters

### -param unnamedParam1

Pointer to a [D3DDDI_UPDATEALLOCPROPERTY](../d3dukmdt/ns-d3dukmdt-d3dddi_updateallocproperty.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

