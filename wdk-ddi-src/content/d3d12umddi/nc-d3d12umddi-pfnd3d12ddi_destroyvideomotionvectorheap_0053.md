---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYVIDEOMOTIONVECTORHEAP_0053
title: PFND3D12DDI_DESTROYVIDEOMOTIONVECTORHEAP_0053
author: windows-driver-content
description: Destroys the video motion vector heap.
ms.assetid: e49d4848-dd80-46b9-91b9-cfdf0eda3311
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_DESTROYVIDEOMOTIONVECTORHEAP_0053
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_DESTROYVIDEOMOTIONVECTORHEAP_0053 callback function

## -description

Destroys the video motion vector heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYVIDEOMOTIONVECTORHEAP_0053 Pfnd3d12ddiDestroyvideomotionvectorheap0053; 

// Definition

VOID Pfnd3d12ddiDestroyvideomotionvectorheap0053 
(
	D3D12DDI_HDEVICE hDrvDevice
	D3D12DDI_HVIDEOMOTIONVECTORHEAP_0053 hDrvMotionEstimator
)
{...}

```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context) that the Direct3D runtime uses.

### -param hDrvMotionEstimator

A handle to the user mode driver motion estimator type.

## -returns

Returns VOID.

## -remarks



## -see-also
