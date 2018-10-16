---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
title: PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
author: windows-driver-content
description: The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU callback function waits for a monitored fence to reach a certain value before processing subsequent context commands.
ms.assetid: 4f71fab2-4776-42bc-b329-aa31ada29550
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
-	PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU callback function

## -description

The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU callback function waits for a monitored fence to reach a certain value before processing subsequent context commands.

## -prototype

```cpp
//Declaration

PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU Pfnd3dkmtWaitforsynchronizationobjectfromgpu; 

// Definition

NTSTATUS Pfnd3dkmtWaitforsynchronizationobjectfromgpu 
(
	const D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromgpu.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
