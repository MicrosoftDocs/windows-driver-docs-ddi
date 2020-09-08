---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORVERTICALBLANKEVENT
title: PFND3DKMT_WAITFORVERTICALBLANKEVENT (d3dkmthk.h)
description: The PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function waits for the vertical blanking interval to occur.
ms.assetid: 3699ca11-e173-4c40-93bc-28b8048e4306
ms.date: 10/19/2018
keywords: ["PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function"]
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
 - PFND3DKMT_WAITFORVERTICALBLANKEVENT
 - d3dkmthk/PFND3DKMT_WAITFORVERTICALBLANKEVENT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_WAITFORVERTICALBLANKEVENT
dev_langs:
 - c++
---

# PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function


## -description

The PFND3DKMT_WAITFORVERTICALBLANKEVENT callback function waits for the vertical blanking interval to occur.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_WAITFORVERTICALBLANKEVENT](ns-d3dkmthk-_d3dkmt_waitforverticalblankevent.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

