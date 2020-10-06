---
UID: NC:d3dkmthk.PFND3DKMT_GETDWMVERTICALBLANKEVENT
title: PFND3DKMT_GETDWMVERTICALBLANKEVENT (d3dkmthk.h)
description: Pfnd3dkmtGetdwmverticalblankevent gets DWM (desktop windows manager) vertical blank event.
ms.assetid: 3f938343-51f7-4e40-bccc-73dbabf9e2a9
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETDWMVERTICALBLANKEVENT callback function"]
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
 - PFND3DKMT_GETDWMVERTICALBLANKEVENT
 - d3dkmthk/PFND3DKMT_GETDWMVERTICALBLANKEVENT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETDWMVERTICALBLANKEVENT
dev_langs:
 - c++
---

# PFND3DKMT_GETDWMVERTICALBLANKEVENT callback function


## -description

Pfnd3dkmtGetdwmverticalblankevent gets DWM (desktop windows manager) vertical blank event.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETVERTICALBLANKEVENT](ns-d3dkmthk-_d3dkmt_getverticalblankevent.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETDWMVERTICALBLANKEVENT Pfnd3dkmtGetdwmverticalblankevent; 

// Definition

NTSTATUS Pfnd3dkmtGetdwmverticalblankevent 
(
	const D3DKMT_GETVERTICALBLANKEVENT *
)
{...}

```

## -remarks

## -see-also

