---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0060
title: PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0060
author: windows-driver-content
description: Creates a video motion vector heap.
tech.root: display
ms.assetid: f1992ba3-04b1-43dc-842e-274e3f55fdde
ms.author: windowsdriverdev
ms.date: 04/04/2019
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
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0060"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0060
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0060 callback function

## -description

Creates a video motion vector heap.

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context) that the Direct3D runtime uses.

### -param pArgs

Pointer to a D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053 structure.

### -param hDrvMotionEstimator

A handle to the user mode driver motion vector heap type.

## -returns

Returns HRESULT.

## -prototype

```
//Declaration

PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0060 Pfnd3d12ddiCreatevideomotionvectorheap0060; 

// Definition

HRESULT Pfnd3d12ddiCreatevideomotionvectorheap0060 
(
	D3D12DDI_HDEVICE hDrvDevice
	 const D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060 *pArgs
	D3D12DDI_HVIDEOMOTIONVECTORHEAP_0053 hDrvMotionEstimator
)
{...}

```

## -remarks

At the API, the Motion Vector Heap object is created to store motion vector output. Motion vector output is opaque at the API.

At the DDI, the runtime will create a standard Resource Buffer. This buffer contains hardware dependent layout. A resolve operation on a compute/3D queue will take this buffer as input and resolve it to the API specified format. The size of this buffer is driver controlled and determined by D3D12DDICAPS_TYPE_VIDEO_0053_MOTION_ESTIMATOR_SIZE capability check of the D3D12DDICAPS_TYPE_VIDEO_0020 enumeration. The buffer may later be used to serialize and deserialize the object for tooling scenarios.

## -see-also

