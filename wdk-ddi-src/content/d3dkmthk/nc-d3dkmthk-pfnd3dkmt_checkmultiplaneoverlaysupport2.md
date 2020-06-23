---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
title: PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 (d3dkmthk.h)
description: The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function checks the details of hardware support for multiplane overlays.
ms.assetid: 2c7e8c79-ec9a-46f1-b217-8e6bd95b21d9
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver:
req.umdf-ver:
req.lib: GDI32.lib
req.dll: GDI32.dll
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
- PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function

## -description

The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function checks the details of hardware support for multiplane overlays.

## -prototype

```cpp
//Declaration

PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 Pfnd3dkmtCheckmultiplaneoverlaysupport2; 

// Definition

NTSTATUS Pfnd3dkmtCheckmultiplaneoverlaysupport2 
(
	D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 *
)
{...}

```

## -parameters

### -param 

[in, out] Pointer to a [D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2](ns-d3dkmthk-_d3dkmt_checkmultiplaneoverlaysupport2.md) structure.

## -returns

Returns NTSTATUS.
