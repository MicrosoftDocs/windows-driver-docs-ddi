---
UID: NC:d3dkmthk.PFND3DKMT_GETSHAREDPRIMARYHANDLE
title: PFND3DKMT_GETSHAREDPRIMARYHANDLE
description: Pfnd3dkmtGetsharedprimaryhandle retrieves the global shared handle for the primary surface.
ms.assetid: 264423b0-f635-4530-a0e8-c9ac3dac9e4c
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
-	PFND3DKMT_GETSHAREDPRIMARYHANDLE
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_GETSHAREDPRIMARYHANDLE callback function

## -description

Pfnd3dkmtGetsharedprimaryhandle retrieves the global shared handle for the primary surface.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETSHAREDPRIMARYHANDLE Pfnd3dkmtGetsharedprimaryhandle; 

// Definition

NTSTATUS Pfnd3dkmtGetsharedprimaryhandle 
(
	D3DKMT_GETSHAREDPRIMARYHANDLE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETSHAREDPRIMARYHANDLE](ns-d3dkmthk-_d3dkmt_getsharedprimaryhandle.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
