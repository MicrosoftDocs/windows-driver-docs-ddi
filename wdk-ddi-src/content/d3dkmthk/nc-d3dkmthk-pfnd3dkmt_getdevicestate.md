---
UID: NC:d3dkmthk.PFND3DKMT_GETDEVICESTATE
title: PFND3DKMT_GETDEVICESTATE
author: windows-driver-content
description: Pfnd3dkmtGetdevicestate retrieves the state of a device.
ms.assetid: 44a7d71a-dca6-4148-8aed-cedac873455a
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
-	PFND3DKMT_GETDEVICESTATE
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_GETDEVICESTATE callback function

## -description

Pfnd3dkmtGetdevicestate retrieves the state of a device.

## -prototype

```cpp
//Declaration

PFND3DKMT_GETDEVICESTATE Pfnd3dkmtGetdevicestate; 

// Definition

NTSTATUS Pfnd3dkmtGetdevicestate 
(
	D3DKMT_GETDEVICESTATE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_GETDEVICESTATE](ns-d3dkmthk-_d3dkmt_getdevicestate.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
