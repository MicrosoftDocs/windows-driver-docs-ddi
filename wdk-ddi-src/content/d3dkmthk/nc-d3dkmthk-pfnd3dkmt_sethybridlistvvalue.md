---
UID: NC:d3dkmthk.PFND3DKMT_SETHYBRIDLISTVVALUE
title: PFND3DKMT_SETHYBRIDLISTVVALUE (d3dkmthk.h)
description: The PFND3DKMT_SETHYBRIDLISTVVALUE callback function sets the hybrid list value.
ms.assetid: 3ab317c8-1ff3-4eaf-80fd-4674f4f52393
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SETHYBRIDLISTVVALUE callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SETHYBRIDLISTVVALUE"
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
- PFND3DKMT_SETHYBRIDLISTVVALUE
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SETHYBRIDLISTVVALUE callback function

## -description

The PFND3DKMT_SETHYBRIDLISTVVALUE callback function sets the hybrid list value.

## -prototype

```cpp
//Declaration

PFND3DKMT_SETHYBRIDLISTVVALUE Pfnd3dkmtSethybridlistvvalue; 

// Definition

NTSTATUS Pfnd3dkmtSethybridlistvvalue 
(
	D3DKMT_HYBRID_LIST *
)
{...}

```

## -parameters

### -param  

Pointer to a [D3DKMT_HYBRID_LIST](ns-d3dkmthk-_d3dkmt_hybrid_list.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
