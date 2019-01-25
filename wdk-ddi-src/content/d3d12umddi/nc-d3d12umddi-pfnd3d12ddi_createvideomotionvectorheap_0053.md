---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0053
title: PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0053 (d3d12umddi.h)
description: Creates a video motion vector heap.
ms.assetid: 4b1ca6fb-cc29-4621-99af-594f42c4e7a9
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
-	PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0053
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0053 callback function

## -description

Creates a video motion vector heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0053 Pfnd3d12ddiCreatevideomotionvectorheap0053; 

// Definition

HRESULT Pfnd3d12ddiCreatevideomotionvectorheap0053 
(
	D3D12DDI_HDEVICE hDrvDevice
	CONST D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053 *pArgs
	D3D12DDI_HVIDEOMOTIONVECTORHEAP_0053 hDrvMotionEstimator
)
{...}

```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context) that the Direct3D runtime uses.

### -param *pArgs

Pointer to a [D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053](ns-d3d12umddi-d3d12ddiarg_create_video_motion_vector_heap_0053.md) structure.

### -param hDrvMotionEstimator

A handle to the user mode driver motion vector heap type.

## -returns

Returns HRESULT.

## -remarks

At the API, the Motion Vector Heap object is created to store motion vector output. Motion vector output is opaque at the API.  

At the DDI, the runtime will create a standard Resource Buffer. This buffer contains hardware dependent layout. A resolve operation on a compute/3D queue will take this buffer as input and resolve it to the API specified format. The size of this buffer is driver controlled and determined by **D3D12DDICAPS_TYPE_VIDEO_0053_MOTION_ESTIMATOR_SIZE** capability check of the [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) enumeration. The buffer may later be used to serialize and deserialize the object for tooling scenarios.



## -see-also
