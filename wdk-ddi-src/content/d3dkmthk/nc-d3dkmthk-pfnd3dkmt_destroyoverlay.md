---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYOVERLAY
title: PFND3DKMT_DESTROYOVERLAY (d3dkmthk.h)
description: The PFND3DKMT_DESTROYOVERLAY callback function disables overlay hardware and deletes the specified overlay handle.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYOVERLAY callback function"]
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
 - PFND3DKMT_DESTROYOVERLAY
 - d3dkmthk/PFND3DKMT_DESTROYOVERLAY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYOVERLAY
dev_langs:
 - c++
---

# PFND3DKMT_DESTROYOVERLAY callback function


## -description

The D3dkmtDestroyOverlay callback function disables overlay hardware and deletes the specified overlay handle.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_DESTROYOVERLAY](ns-d3dkmthk-_d3dkmt_destroyoverlay.md) structure.

## -returns

Returns NTSTATUS.

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

