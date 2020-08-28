---
UID: NC:d3dkmthk.PFND3DKMT_UPDATEGPUVIRTUALADDRESS
title: PFND3DKMT_UPDATEGPUVIRTUALADDRESS (d3dkmthk.h)
description: The PFND3DKMT_UPDATEGPUVIRTUALADDRESS callback function allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.
ms.assetid: 024f77b9-705e-4fcc-88c0-1d903aa7b951
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UPDATEGPUVIRTUALADDRESS callback function"]
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
 - PFND3DKMT_UPDATEGPUVIRTUALADDRESS
 - d3dkmthk/PFND3DKMT_UPDATEGPUVIRTUALADDRESS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_UPDATEGPUVIRTUALADDRESS
dev_langs:
 - c++
---

# PFND3DKMT_UPDATEGPUVIRTUALADDRESS callback function


## -description

The PFND3DKMT_UPDATEGPUVIRTUALADDRESS callback function allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_UPDATEGPUVIRTUALADDRESS](ns-d3dkmthk-_d3dkmt_updategpuvirtualaddress.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_UPDATEGPUVIRTUALADDRESS Pfnd3dkmtUpdategpuvirtualaddress; 

// Definition

NTSTATUS Pfnd3dkmtUpdategpuvirtualaddress 
(
	const D3DKMT_UPDATEGPUVIRTUALADDRESS *
)
{...}

```

## -remarks

## -see-also

