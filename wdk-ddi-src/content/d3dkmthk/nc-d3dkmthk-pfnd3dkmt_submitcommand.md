---
UID: NC:d3dkmthk.PFND3DKMT_SUBMITCOMMAND
title: PFND3DKMT_SUBMITCOMMAND
author: windows-driver-content
description: The PFND3DKMT_SUBMITCOMMAND callback function is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
ms.assetid: 1c4650b3-31ef-4432-908d-fb8511727686
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
-	PFND3DKMT_SUBMITCOMMAND
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SUBMITCOMMAND callback function

## -description

The PFND3DKMT_SUBMITCOMMAND callback function is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.

## -prototype

```cpp
//Declaration

PFND3DKMT_SUBMITCOMMAND Pfnd3dkmtSubmitcommand; 

// Definition

NTSTATUS Pfnd3dkmtSubmitcommand 
(
	const D3DKMT_SUBMITCOMMAND *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SUBMITCOMMAND](ns-d3dkmthk-_d3dkmt_submitcommand.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
