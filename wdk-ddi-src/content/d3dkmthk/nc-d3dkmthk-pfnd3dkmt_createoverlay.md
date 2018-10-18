---
UID: NC:d3dkmthk.PFND3DKMT_CREATEOVERLAY
title: PFND3DKMT_CREATEOVERLAY
author: windows-driver-content
description: The PFND3DKMT_CREATEOVERLAY callback function enables the overlay hardware if the hardware is capable.
ms.assetid: 2908f347-a341-4603-95db-3f92b77afc88
ms.date: 
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
-	PFND3DKMT_CREATEOVERLAY
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_CREATEOVERLAY callback function

## -description

The PFND3DKMT_CREATEOVERLAY callback function enables the overlay hardware if the hardware is capable.

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

## -parameters

### -param *

[in, out] Pointer to a [D3DKMT_CREATEOVERLAY](ns-d3dkmthk-_d3dkmt_createoverlay.md) structure.

## -returns

Returns NTSTATUS.
