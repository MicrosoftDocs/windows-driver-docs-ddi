---
UID: NC:d3dkmthk.PFND3DKMT_FLIPOVERLAY
title: PFND3DKMT_FLIPOVERLAY
author: windows-driver-content
description: The Pfnd3dkmtFlipoverlay callback function displays a new allocation by using the specified overlay.
ms.assetid: 29cd8d93-c162-47a4-9ac3-808e705819c0
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
-	PFND3DKMT_FLIPOVERLAY
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_FLIPOVERLAY callback function

## -description

The Pfnd3dkmtFlipoverlay callback function displays a new allocation by using the specified overlay.

## -prototype

```
//Declaration

PFND3DKMT_FLIPOVERLAY Pfnd3dkmtFlipoverlay; 

// Definition

NTSTATUS Pfnd3dkmtFlipoverlay 
(
	const D3DKMT_FLIPOVERLAY *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_FLIPOVERLAY](ns-d3dkmthk-_d3dkmt_flipoverlay.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also