---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
title: PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 (d3dkmthk.h)
description: The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function checks the details of hardware support for multiplane overlays.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function"]
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
 - PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
 - d3dkmthk/PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
dev_langs:
 - c++
---

# PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function


## -description

The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function checks the details of hardware support for multiplane overlays.

## -parameters

### -param unnamedParam1 [in, out]

Pointer to a [D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3](ns-d3dkmthk-_d3dkmt_checkmultiplaneoverlaysupport3.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 Pfnd3dkmtCheckmultiplaneoverlaysupport3; 

// Definition

NTSTATUS Pfnd3dkmtCheckmultiplaneoverlaysupport3 
(
	D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 *
)
{...}

```

