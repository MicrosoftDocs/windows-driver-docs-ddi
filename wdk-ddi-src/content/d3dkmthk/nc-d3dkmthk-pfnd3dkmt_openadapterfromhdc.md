---
UID: NC:d3dkmthk.PFND3DKMT_OPENADAPTERFROMHDC
title: PFND3DKMT_OPENADAPTERFROMHDC
author: windows-driver-content
description: Pfnd3dkmtOpenadapterfromhdc maps a device context handle (HDC) to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
ms.assetid: 656f43e8-ed2d-4f09-99c0-25d054b0c6ff
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
-	PFND3DKMT_OPENADAPTERFROMHDC
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_OPENADAPTERFROMHDC callback function

## -description

Pfnd3dkmtOpenadapterfromhdc maps a device context handle (HDC) to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENADAPTERFROMHDC Pfnd3dkmtOpenadapterfromhdc; 

// Definition

NTSTATUS Pfnd3dkmtOpenadapterfromhdc 
(
	D3DKMT_OPENADAPTERFROMHDC *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENADAPTERFROMHDC](ns-d3dkmthk-_d3dkmt_openadapterfromhdc.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
