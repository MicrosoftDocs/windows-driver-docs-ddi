---
UID: NC:d3dkmthk.PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
title: PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
author: windows-driver-content
description: The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU callback function is used to signal a monitored fence.
ms.assetid: e9e3ae87-849b-40ff-b7f4-e9560a6ef9bd
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
-	PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU callback function

## -description

The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU callback function is used to signal a monitored fence.

## -prototype

```cpp
//Declaration

PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU Pfnd3dkmtSignalsynchronizationobjectfromgpu; 

// Definition

NTSTATUS Pfnd3dkmtSignalsynchronizationobjectfromgpu 
(
	const D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
