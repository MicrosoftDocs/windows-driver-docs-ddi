---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
title: PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 (d3dkmthk.h)
description: The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function checks the details of hardware support for multiplane overlays.
ms.assetid: 2c7e8c79-ec9a-46f1-b217-8e6bd95b21d9
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
 - d3dkmthk/PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
dev_langs:
 - c++
---

# PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function

> [!NOTE] This function has been replaced by [PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3](nc-d3dkmthk-pfnd3dkmt_checkmultiplaneoverlaysupport3.md).


## -description

The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function checks the details of hardware support for multiplane overlays.

## -parameters

### -param Arg1

[in, out] Pointer to a [D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2](ns-d3dkmthk-_d3dkmt_checkmultiplaneoverlaysupport2.md) structure.

## -returns

Returns NTSTATUS.

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

