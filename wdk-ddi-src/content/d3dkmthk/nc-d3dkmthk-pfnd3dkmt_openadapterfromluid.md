---
UID: NC:d3dkmthk.PFND3DKMT_OPENADAPTERFROMLUID
title: PFND3DKMT_OPENADAPTERFROMLUID
author: windows-driver-content
description: Pfnd3dkmtOpenadapterfromluid maps a locally unique identifier (LUID) to a graphics adapter handle.
ms.assetid: 14e613a4-3b9a-4c8c-aa87-c75ed773b7a1
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
-	PFND3DKMT_OPENADAPTERFROMLUID
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_OPENADAPTERFROMLUID callback function

## -description

Pfnd3dkmtOpenadapterfromluid maps a locally unique identifier (LUID) to a graphics adapter handle.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENADAPTERFROMLUID Pfnd3dkmtOpenadapterfromluid; 

// Definition

NTSTATUS Pfnd3dkmtOpenadapterfromluid 
(
	D3DKMT_OPENADAPTERFROMLUID *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENADAPTERFROMLUID](ns-d3dkmthk-_d3dkmt_openadapterfromluid.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
