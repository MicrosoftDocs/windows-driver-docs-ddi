---
UID: NC:d3dkmthk.PFND3DKMT_CREATEOVERLAY
title: PFND3DKMT_CREATEOVERLAY (d3dkmthk.h)
description: The PFND3DKMT_CREATEOVERLAY callback function enables the overlay hardware if the hardware is capable.
ms.assetid: 2908f347-a341-4603-95db-3f92b77afc88
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATEOVERLAY callback function"]
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
 - PFND3DKMT_CREATEOVERLAY
 - d3dkmthk/PFND3DKMT_CREATEOVERLAY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATEOVERLAY
dev_langs:
 - c++
---

# PFND3DKMT_CREATEOVERLAY callback function


## -description

The PFND3DKMT_CREATEOVERLAY callback function enables the overlay hardware if the hardware is capable.

## -parameters

### -param Arg1

[in, out] Pointer to a [D3DKMT_CREATEOVERLAY](ns-d3dkmthk-_d3dkmt_createoverlay.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATEOVERLAY Pfnd3dkmtCreateoverlay; 

// Definition

NTSTATUS Pfnd3dkmtCreateoverlay 
(
	D3DKMT_CREATEOVERLAY *
)
{...}

```

