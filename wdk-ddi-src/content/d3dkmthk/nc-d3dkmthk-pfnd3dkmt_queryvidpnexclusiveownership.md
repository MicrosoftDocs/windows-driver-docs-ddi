---
UID: NC:d3dkmthk.PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP
title: PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP (d3dkmthk.h)
description: The PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP callback function queries for VidPn exclusive ownership.
ms.assetid: af3082f5-6afd-4a93-b0d4-a5411e0f41df
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP"
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
- PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP callback function

## -description

The PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP callback function queries for VidPn exclusive ownership.

## -prototype

```cpp
//Declaration

PFND3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP Pfnd3dkmtQueryvidpnexclusiveownership; 

// Definition

NTSTATUS Pfnd3dkmtQueryvidpnexclusiveownership 
(
	D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_QUERYVIDPNEXCLUSIVEOWNERSHIP](ns-d3dkmthk-_d3dkmt_queryvidpnexclusiveownership.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
