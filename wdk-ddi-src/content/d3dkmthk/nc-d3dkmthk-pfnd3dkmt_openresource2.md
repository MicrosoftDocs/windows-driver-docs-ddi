---
UID: NC:d3dkmthk.PFND3DKMT_OPENRESOURCE2
title: PFND3DKMT_OPENRESOURCE2 (d3dkmthk.h)
description: Pfnd3dkmtOpenresource2 opens a shared resource.
ms.assetid: ce4cbbfe-fdae-4bb8-91db-9da4a992f0ce
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_OPENRESOURCE2"
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
- PFND3DKMT_OPENRESOURCE2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_OPENRESOURCE2 callback function

## -description

Pfnd3dkmtOpenresource2 opens a shared resource.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENRESOURCE2 Pfnd3dkmtOpenresource2; 

// Definition

NTSTATUS Pfnd3dkmtOpenresource2 
(
	D3DKMT_OPENRESOURCE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENRESOURCE](ns-d3dkmthk-_d3dkmt_openresource.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
