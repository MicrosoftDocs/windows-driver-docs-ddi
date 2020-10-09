---
UID: NC:d3dkmthk.PFND3DKMT_GETOVERLAYSTATE
title: PFND3DKMT_GETOVERLAYSTATE (d3dkmthk.h)
description: Pfnd3dkmtGetoverlaystate retrieves the status about an overlay.
ms.assetid: 0cad9f03-12b6-4039-9a8a-db420644288b
ms.date: 10/19/2018
keywords: ["PFND3DKMT_GETOVERLAYSTATE callback function"]
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
 - PFND3DKMT_GETOVERLAYSTATE
 - d3dkmthk/PFND3DKMT_GETOVERLAYSTATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETOVERLAYSTATE
dev_langs:
 - c++
---

# PFND3DKMT_GETOVERLAYSTATE callback function


## -description

Pfnd3dkmtGetoverlaystate retrieves the status about an overlay.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_GETOVERLAYSTATE](ns-d3dkmthk-_d3dkmt_getoverlaystate.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETOVERLAYSTATE Pfnd3dkmtGetoverlaystate; 

// Definition

NTSTATUS Pfnd3dkmtGetoverlaystate 
(
	D3DKMT_GETOVERLAYSTATE *
)
{...}

```

## -remarks

## -see-also

