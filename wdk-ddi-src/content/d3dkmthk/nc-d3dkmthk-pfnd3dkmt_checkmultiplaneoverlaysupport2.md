---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
title: PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
author: windows-driver-content
description: The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2 callback function checks the details of hardware support for multiplane overlays.
ms.assetid: 2c7e8c79-ec9a-46f1-b217-8e6bd95b21d9
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2
product:
-	Windows
targetos: Windows
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

### -param *

[in, out] Pointer to a [D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2](ns-d3dkmthk-_d3dkmt_checkmultiplaneoverlaysupport2.md) structure.

## -returns

Returns NTSTATUS.
