---
UID: NC:d3dkmthk.PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
title: PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
description: Pfnd3dkmtOpenadapterfromgdidisplayname maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
ms.assetid: 35d38a98-e55e-4966-bd2c-7a22da9e3143
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
-	PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME callback function

## -description

Pfnd3dkmtOpenadapterfromgdidisplayname maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME Pfnd3dkmtOpenadapterfromgdidisplayname; 

// Definition

NTSTATUS Pfnd3dkmtOpenadapterfromgdidisplayname 
(
	D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME](ns-d3dkmthk-_d3dkmt_openadapterfromgdidisplayname.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
