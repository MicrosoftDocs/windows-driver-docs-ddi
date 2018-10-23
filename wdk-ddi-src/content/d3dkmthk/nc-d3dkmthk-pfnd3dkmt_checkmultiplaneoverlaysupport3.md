---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
title: PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
author: windows-driver-content
description: The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function checks the details of hardware support for multiplane overlays.
ms.assetid: 4126253d-6fa7-42ab-8948-f055516f3b26
ms.date: 10/19/2018
ms.topic: callback
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function

## -description

The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 callback function checks the details of hardware support for multiplane overlays.

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

## -parameters

### -param *

[in, out] Pointer to a [D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3](ns-d3dkmthk-_d3dkmt_checkmultiplaneoverlaysupport3.md) structure.

## -returns

Returns NTSTATUS.
