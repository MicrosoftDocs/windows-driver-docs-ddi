---
UID: NC:d3dkmthk.PFND3DKMT_GETDWMVERTICALBLANKEVENT
title: PFND3DKMT_GETDWMVERTICALBLANKEVENT (d3dkmthk.h)
description: Pfnd3dkmtGetdwmverticalblankevent gets DWM (desktop windows manager) vertical blank event.
ms.assetid: 3f938343-51f7-4e40-bccc-73dbabf9e2a9
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmthk/PFND3DKMT_GETDWMVERTICALBLANKEVENT"
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
- PFND3DKMT_GETDWMVERTICALBLANKEVENT
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_GETDWMVERTICALBLANKEVENT callback function

## -description

Pfnd3dkmtGetdwmverticalblankevent gets DWM (desktop windows manager) vertical blank event.

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

## -parameters

### -param * 

Pointer to a [D3DKMT_GETVERTICALBLANKEVENT](ns-d3dkmthk-_d3dkmt_getverticalblankevent.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
