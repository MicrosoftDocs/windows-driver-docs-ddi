---
UID: NC:d3dkmthk.PFND3DKMT_ESCAPE
title: PFND3DKMT_ESCAPE (d3dkmthk.h)
description: The Pfnd3dkmtEscape callback function shares info with the kernel mode display driver.
ms.assetid: a23f8430-f752-440b-a7bf-f07eede5e889
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
-	PFND3DKMT_ESCAPE
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_ESCAPE callback function

## -description

The Pfnd3dkmtEscape callback function shares info with the kernel mode display driver.

## -prototype

```cpp
//Declaration

PFND3DKMT_ESCAPE Pfnd3dkmtEscape; 

// Definition

NTSTATUS Pfnd3dkmtEscape 
(
	const D3DKMT_ESCAPE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_ESCAPE](ns-d3dkmthk-_d3dkmt_escape.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
