---
UID: NC:d3dkmthk.PFND3DKMT_UPDATEOVERLAY
title: PFND3DKMT_UPDATEOVERLAY (d3dkmthk.h)
description: PFND3DKMT_UPDATEOVERLAY callback function modifies a kernel-mode overlay object.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UPDATEOVERLAY callback function"]
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
 - PFND3DKMT_UPDATEOVERLAY
 - d3dkmthk/PFND3DKMT_UPDATEOVERLAY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_UPDATEOVERLAY
dev_langs:
 - c++
---

# PFND3DKMT_UPDATEOVERLAY callback function


## -description

PFND3DKMT_UPDATEOVERLAY callback function modifies a kernel-mode overlay object.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_UPDATEOVERLAY](ns-d3dkmthk-_d3dkmt_updateoverlay.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_UPDATEOVERLAY Pfnd3dkmtUpdateoverlay; 

// Definition

NTSTATUS Pfnd3dkmtUpdateoverlay 
(
	const D3DKMT_UPDATEOVERLAY *
)
{...}

```

## -remarks

## -see-also

