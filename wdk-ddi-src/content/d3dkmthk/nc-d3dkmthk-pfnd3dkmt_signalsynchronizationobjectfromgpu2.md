---
UID: NC:d3dkmthk.PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
title: PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 (d3dkmthk.h)
description: The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 callback function is used to signal a monitored fence.
ms.assetid: f37d2a36-680a-43b7-84f5-8ce2b23b609e
ms.date: 10/19/2018
keywords: ["PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 callback function

## -description

The PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 callback function is used to signal a monitored fence.

## -prototype

```cpp
//Declaration

PFND3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 Pfnd3dkmtSignalsynchronizationobjectfromgpu2; 

// Definition

NTSTATUS Pfnd3dkmtSignalsynchronizationobjectfromgpu2 
(
	const D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 *
)
{...}

```

## -parameters

### -param  

Pointer to a [D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu2.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
