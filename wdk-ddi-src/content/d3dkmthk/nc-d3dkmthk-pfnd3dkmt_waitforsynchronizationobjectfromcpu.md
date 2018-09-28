---
UID: NC:d3dkmthk.PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
title: PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
author: windows-driver-content
description: The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU callback function waits for a monitored fence to reach a certain value.
ms.assetid: f83db141-f319-4cc3-9544-b0d98f0ce76a
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
-	PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU callback function

## -description

The PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU callback function waits for a monitored fence to reach a certain value. 

## -prototype

```
//Declaration

PFND3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU Pfnd3dkmtWaitforsynchronizationobjectfromcpu; 

// Definition

NTSTATUS Pfnd3dkmtWaitforsynchronizationobjectfromcpu 
(
	const D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromcpu.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also