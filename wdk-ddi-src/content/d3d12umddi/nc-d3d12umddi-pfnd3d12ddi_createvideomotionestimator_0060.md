---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0060
title: PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0060
author: windows-driver-content
description: Creates the video motion estimator.
tech.root: display
ms.assetid: e1606f4a-88ed-48e0-8562-9cd27f2498ff
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0060"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
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
 - PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0060
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0060 callback function

## -description

Creates the video motion estimator.


## -prototype

```
//Declaration

PFND3D12DDI_CREATEVIDEOMOTIONESTIMATOR_0060 Pfnd3d12ddiCreatevideomotionestimator0060; 

// Definition

HRESULT Pfnd3d12ddiCreatevideomotionestimator0060 
(
	D3D12DDI_HDEVICE hDrvDevice
	 const D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060 *pArgs
	D3D12DDI_HVIDEOMOTIONESTIMATOR_0053 hDrvMotionEstimator
)
{...}

```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context) that the Direct3D runtime uses.

### -param *pArgs

Pointer to a [D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060](ns-d3d12umddi-d3d12ddiarg_create_video_motion_estimator_0060.md) structure.

### -param hDrvMotionEstimator

A handle to a D3D12DDI_HVIDEOMOTIONESTIMATOR_0053 that represents the user mode driver motion estimator type.

## -returns

Returns HRESULT.

## -remarks

The motion estimation operation must support reading from and writing to hardware DRM protected resources when the driver supports Direct3D protected resource support. If the inputs are hardware DRM protected, the runtime will require that the output is a hardware DRM protected resource. 

The motion estimation operation is assumed to write to both the D3D12DDI_HVIDEOMOTIONESTIMATOR_0053 context object and to the D3D12DDI_HVIDEOMOTIONVECTORHEAP_0053, so these must be created with a protected resource session when the input textures are protected.

## -see-also
