---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0053
title: PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0053 (d3d12umddi.h)
description: Creates the video motion estimator.
ms.assetid: 044c1e98-b151-42dc-ab5b-1f137460e9f4
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0053 callback function

## -description

Creates the video motion estimator.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0053 Pfnd3d12ddiCreatevideomotionestimator0053; 

// Definition

HRESULT Pfnd3d12ddiCreatevideomotionestimator0053 
(
	D3D12DDI_HDEVICE hDrvDevice
	CONST D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053 *pArgs
	D3D12DDI_HVIDEOMOTIONESTIMATOR_0053 hDrvMotionEstimator
)
{...}

```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context) that the Direct3D runtime uses.

### -param *pArgs

Pointer to a [D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053](ns-d3d12umddi-d3d12ddiarg_create_video_motion_estimator_0053.md) structure.

### -param hDrvMotionEstimator


A handle to the user mode driver motion estimator type.

## -returns

Returns HRESULT.

## -remarks

The motion estimation operation must support reading from and writing to hardware DRM protected resources when the driver supports Direct3D protected resource support. If the inputs are hardware DRM protected, the runtime will require that the output is a hardware DRM protected resource. 

The motion estimation operation is assumed to write to both the D3D12DDI_HVIDEOMOTIONESTIMATOR_0053 context object and to the D3D12DDI_HVIDEOMOTIONVECTORHEAP_0053, so these must be created with a protected resource session when the input textures are protected.

## -see-also
