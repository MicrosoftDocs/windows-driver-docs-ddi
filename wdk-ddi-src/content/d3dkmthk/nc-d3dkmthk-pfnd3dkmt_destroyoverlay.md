---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYOVERLAY
title: PFND3DKMT_DESTROYOVERLAY (d3dkmthk.h)
description: The PFND3DKMT_DESTROYOVERLAY callback function disables overlay hardware and deletes the specified overlay handle.
ms.assetid: 28e665a1-8278-49ed-bfe8-2a28596967df
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/PFND3DKMT_DESTROYOVERLAY"
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
- PFND3DKMT_DESTROYOVERLAY
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_DESTROYOVERLAY callback function

## -description

The D3dkmtDestroyOverlay callback function disables overlay hardware and deletes the specified overlay handle.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYOVERLAY Pfnd3dkmtDestroyoverlay; 

// Definition

NTSTATUS Pfnd3dkmtDestroyoverlay 
(
	const D3DKMT_DESTROYOVERLAY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_DESTROYOVERLAY](ns-d3dkmthk-_d3dkmt_destroyoverlay.md) structure.

## -returns

Returns NTSTATUS.
