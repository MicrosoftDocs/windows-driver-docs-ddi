---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORVERTICALBLANKEVENT2
title: PFND3DKMT_WAITFORVERTICALBLANKEVENT2 (d3dkmthk.h)
description: The PFND3DKMT_WAITFORVERTICALBLANKEVENT2 callback function waits for the vertical blanking interval to occur.
ms.assetid: d6dcb757-d6e9-4119-814e-8cace8dc0603
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_WAITFORVERTICALBLANKEVENT2
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_WAITFORVERTICALBLANKEVENT2 callback function

## -description

The PFND3DKMT_WAITFORVERTICALBLANKEVENT2 callback function waits for the vertical blanking interval to occur.

## -prototype

```cpp
//Declaration

PFND3DKMT_WAITFORVERTICALBLANKEVENT2 Pfnd3dkmtWaitforverticalblankevent2; 

// Definition

NTSTATUS Pfnd3dkmtWaitforverticalblankevent2 
(
	const D3DKMT_WAITFORVERTICALBLANKEVENT2 *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_WAITFORVERTICALBLANKEVENT2](ns-d3dkmthk-_d3dkmt_waitforverticalblankevent2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
