---
UID: NC:d3dkmthk.PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID
title: PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID (d3dkmthk.h)
description: Pfnd3dkmtGetsharedresourceadapterluid maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID callback function"]
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
 - PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID
 - d3dkmthk/PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID
dev_langs:
 - c++
---

# PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID callback function


## -description

Pfnd3dkmtGetsharedresourceadapterluid maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETSHAREDRESOURCEADAPTERLUID](ns-d3dkmthk-_d3dkmt_getsharedresourceadapterluid.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETSHAREDRESOURCEADAPTERLUID Pfnd3dkmtGetsharedresourceadapterluid; 

// Definition

NTSTATUS Pfnd3dkmtGetsharedresourceadapterluid 
(
	D3DKMT_GETSHAREDRESOURCEADAPTERLUID *
)
{...}

```

## -remarks

## -see-also

