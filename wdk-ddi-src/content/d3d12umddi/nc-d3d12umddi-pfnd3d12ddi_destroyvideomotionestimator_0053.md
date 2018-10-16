---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYVIDEOMOTIONESTIMATOR_0053
title: PFND3D12DDI_DESTROYVIDEOMOTIONESTIMATOR_0053
author: windows-driver-content
description: Destroys the video motion estimator.
ms.assetid: 6d142a01-4ba6-4d72-b5ae-19a5117f4448
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3D12DDI_DESTROYVIDEOMOTIONESTIMATOR_0053
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_DESTROYVIDEOMOTIONESTIMATOR_0053 callback function

## -description

Destroys the video motion estimator.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYVIDEOMOTIONESTIMATOR_0053 Pfnd3d12ddiDestroyvideomotionestimator0053; 

// Definition

VOID Pfnd3d12ddiDestroyvideomotionestimator0053 
(
	D3D12DDI_HDEVICE hDrvDevice
	D3D12DDI_HVIDEOMOTIONESTIMATOR_0053 hDrvMotionEstimator
)
{...}

```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context) that the Direct3D runtime uses.

### -param hDrvMotionEstimator: 

A handle to the user mode driver motion estimator type.

## -returns

Returns VOID.

## -remarks




## -see-also
