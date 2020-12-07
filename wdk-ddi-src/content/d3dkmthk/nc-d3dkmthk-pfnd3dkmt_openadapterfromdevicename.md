---
UID: NC:d3dkmthk.PFND3DKMT_OPENADAPTERFROMDEVICENAME
title: PFND3DKMT_OPENADAPTERFROMDEVICENAME (d3dkmthk.h)
description: Pfnd3dkmtOpenadapterfromdevicename maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OPENADAPTERFROMDEVICENAME callback function"]
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
 - PFND3DKMT_OPENADAPTERFROMDEVICENAME
 - d3dkmthk/PFND3DKMT_OPENADAPTERFROMDEVICENAME
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OPENADAPTERFROMDEVICENAME
dev_langs:
 - c++
---

# PFND3DKMT_OPENADAPTERFROMDEVICENAME callback function


## -description

Pfnd3dkmtOpenadapterfromdevicename maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OPENADAPTERFROMDEVICENAME](ns-d3dkmthk-_d3dkmt_openadapterfromdevicename.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_OPENADAPTERFROMDEVICENAME Pfnd3dkmtOpenadapterfromdevicename; 

// Definition

NTSTATUS Pfnd3dkmtOpenadapterfromdevicename 
(
	D3DKMT_OPENADAPTERFROMDEVICENAME *
)
{...}

```

## -remarks

## -see-also

