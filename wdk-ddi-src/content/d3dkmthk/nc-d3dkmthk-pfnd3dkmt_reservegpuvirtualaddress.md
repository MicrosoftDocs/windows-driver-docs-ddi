---
UID: NC:d3dkmthk.PFND3DKMT_RESERVEGPUVIRTUALADDRESS
title: PFND3DKMT_RESERVEGPUVIRTUALADDRESS (d3dkmthk.h)
description: The PFND3DKMT_RESERVEGPUVIRTUALADDRESS callback function reserves an address range in the current process graphics processing unit (GPU) virtual address space.
ms.assetid: fdb36907-4288-4dfd-bcb6-63fc1092ea6c
ms.date: 10/19/2018
keywords: ["PFND3DKMT_RESERVEGPUVIRTUALADDRESS callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_RESERVEGPUVIRTUALADDRESS"
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
- PFND3DKMT_RESERVEGPUVIRTUALADDRESS
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_RESERVEGPUVIRTUALADDRESS callback function

## -description

The PFND3DKMT_RESERVEGPUVIRTUALADDRESS callback function reserves an address range in the current process graphics processing unit (GPU) virtual address space.

## -prototype

```cpp
//Declaration

PFND3DKMT_RESERVEGPUVIRTUALADDRESS Pfnd3dkmtReservegpuvirtualaddress; 

// Definition

NTSTATUS Pfnd3dkmtReservegpuvirtualaddress 
(
	D3DDDI_RESERVEGPUVIRTUALADDRESS *
)
{...}

```

## -parameters

### -param  

Pointer to a [D3DDDI_RESERVEGPUVIRTUALADDRESS](../d3dukmdt/ns-d3dukmdt-d3dddi_reservegpuvirtualaddress.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
