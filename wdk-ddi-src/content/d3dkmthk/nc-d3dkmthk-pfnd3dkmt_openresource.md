---
UID: NC:d3dkmthk.PFND3DKMT_OPENRESOURCE
title: PFND3DKMT_OPENRESOURCE (d3dkmthk.h)
description: Pfnd3dkmtOpenresource opens a shared resource.
ms.assetid: 02623395-6774-457a-ab73-17e68216d812
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_OPENRESOURCE"
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
- PFND3DKMT_OPENRESOURCE
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_OPENRESOURCE callback function

## -description

Pfnd3dkmtOpenresource opens a shared resource.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENRESOURCE Pfnd3dkmtOpenresource; 

// Definition

NTSTATUS Pfnd3dkmtOpenresource 
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
