---
UID: NC:d3d12umddi.PFND3D12DDI_ESTIMATE_MOTION_0053
title: PFND3D12DDI_ESTIMATE_MOTION_0053 (d3d12umddi.h)
description: Performs the motion estimation operation.
ms.assetid: 52009f15-ea7a-4993-adce-c3b0a3b1e5ee
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
- PFND3D12DDI_ESTIMATE_MOTION_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_ESTIMATE_MOTION_0053 callback function

## -description

Performs the motion estimation operation.

## -prototype

```cpp
//Declaration

PFND3D12DDI_ESTIMATE_MOTION_0053 Pfnd3d12ddiEstimateMotion0053; 

// Definition

VOID Pfnd3d12ddiEstimateMotion0053 
(
	D3D12DDI_HCOMMANDLIST hDrvCommandList
	D3D12DDI_HVIDEOMOTIONESTIMATOR_0053 hDrvMotionEstimator
	CONST D3D12DDI_VIDEO_MOTION_ESTIMATOR_OUTPUT_0053 *pOutputArguments
	CONST D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053 *pInputArguments
)
{...}

```

## -parameters

### -param hDrvCommandList

Driver handle for a video encode command list.

### -param hDrvMotionEstimator

Handle to the motion estimator context object.

### -param *pOutputArguments

Pointer to a [D3D12DDI_VIDEO_MOTION_ESTIMATOR_OUTPUT_0053](ns-d3d12umddi-d3d12ddi_video_motion_estimator_output_0053.md) structure that contains the output arguments for the motion estimation operation.

### -param *pInputArguments

Pointer to a [D3D12DDI_VIDEO_MOTION_ESTIMATOR_INPUT_0053](ns-d3d12umddi-d3d12ddi_video_motion_estimator_input_0053.md) structure that contains the input arguments for the motion estimation operation.

## -returns

Returns VOID.

## -remarks

The motion estimation operation has a context object to associate the lifetime of internal allocations needed to perform the operation. All allocations associated with his object should be allocated when the object is created and deallocated when the object is de-allocated. This should include any buffers used as temporary/scratch storage. 

Operations against this object may be recorded to command lists in a different order than execution. No two API queue instances may be executing command lists containing this object at the same time and expect valid results. The application is responsible for synchronizing access across multiple queue instances.

This object must support [PFND3D12DDI_MAKERESIDENT](nc-d3d12umddi-pfnd3d12ddi_makeresident_cb.md), [PFND3D12DDI_EVICT](nc-d3d12umddi-pfnd3d12ddi_evict_cb.md), and [PFND3D12DDI_GET_DEBUG_ALLOCATION_INFO](nc-d3d12umddi-pfnd3d12ddi_get_debug_allocation_info_0012.md).

## -see-also
