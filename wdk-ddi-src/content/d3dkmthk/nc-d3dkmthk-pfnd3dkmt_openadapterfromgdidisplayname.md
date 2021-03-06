---
UID: NC:d3dkmthk.PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
title: PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME (d3dkmthk.h)
description: Pfnd3dkmtOpenadapterfromgdidisplayname maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
 - d3dkmthk/PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
dev_langs:
 - c++
---

# PFND3DKMT_OPENADAPTERFROMGDIDISPLAYNAME callback function


## -description

Pfnd3dkmtOpenadapterfromgdidisplayname maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME](ns-d3dkmthk-_d3dkmt_openadapterfromgdidisplayname.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

