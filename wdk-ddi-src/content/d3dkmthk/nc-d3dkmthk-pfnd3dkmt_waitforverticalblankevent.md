---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORVERTICALBLANKEVENT
title: PFND3DKMT_WAITFORVERTICALBLANKEVENT (d3dkmthk.h)
description: The PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function waits for the vertical blanking interval to occur.
ms.assetid: 3699ca11-e173-4c40-93bc-28b8048e4306
ms.date: 10/19/2018
keywords: ["PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_WAITFORVERTICALBLANKEVENT"
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
- PFND3DKMT_WAITFORVERTICALBLANKEVENT
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function

## -description

The PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function waits for the vertical blanking interval to occur.

## -prototype

```cpp
//Declaration

PFND3DKMT_WAITFORVERTICALBLANKEVENT Pfnd3dkmtWaitforverticalblankevent; 

// Definition

NTSTATUS Pfnd3dkmtWaitforverticalblankevent 
(
	const D3DKMT_WAITFORVERTICALBLANKEVENT *
)
{...}

```

## -parameters

### -param  

Pointer to a [D3DKMT_WAITFORVERTICALBLANKEVENT](ns-d3dkmthk-_d3dkmt_waitforverticalblankevent.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
