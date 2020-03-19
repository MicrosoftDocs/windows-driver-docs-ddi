---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
title: PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT (d3dkmthk.h)
description: The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function checks the details of hardware support for multiplane overlays.
ms.assetid: d67108d9-c3fa-41dc-ac6f-79243c1f7b68
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function

## -description

The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function checks the details of hardware support for multiplane overlays.

## -prototype

```cpp
//Declaration

PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT Pfnd3dkmtCheckmultiplaneoverlaysupport; 

// Definition

NTSTATUS Pfnd3dkmtCheckmultiplaneoverlaysupport 
(
	D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT *
)
{...}

```

## -parameters

### -param *

[in, out] Pointer to a [D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT](ns-d3dkmthk-_d3dkmt_checkmultiplaneoverlaysupport.md) structure.

## -returns

Returns NTSTATUS.
