---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053
title: D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053 (d3d12umddi.h)
description: The video capability check for motion estimation size.
ms.assetid: 7b0578ac-afde-4356-ac90-c906f8c91487
ms.date: 10/23/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053"
ms.keywords: D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053, D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_VIDEO_MOTION_ESTIMATOR_SIZE_DATA_0053 structure

## -description

This capability determines the residency size for the motion estimator and the hardware dependent output buffer when called with the same creation parameters.

## -struct-fields

### -field NodeMask

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to. 

### -field InputFormat

The DXGI_FORMAT of the input frame and reference frame. Currently, only DXGI_FORMAT_NV12 is allowed.

### -field BlockSize

The block size to use with the motion estimator. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SEARCH_BLOCK_SIZE_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_search_block_size_0053.md).

### -field Precision

The precision to use with the motion estimator. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_VECTOR_PRECISION_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_vector_precision_0053.md).

### -field DifferencesMetric

Indicates the differences metric to capture during motion estimation. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_DIFFERENCES_METRIC_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_differences_metric_0053.md).

### -field SizeRange

The size range allowed with the Motion Estimator. This may be a subset of the size range supported by the driver to optimize memory usage. See [D3D12DDI_VIDEO_SIZE_RANGE_0032](ns-d3d12umddi-d3d12ddi_video_size_range_0032.md).

### -field Protected

TRUE if the motion estimator operates on protected resource input and produces protected output.  The driver must also support protected resources for D3D12 to set TRUE.  FALSE otherwise.

### -field MotionEstimatorMemoryPoolL0Size

Output memory pool size.

### -field MotionEstimatorMemoryPoolL1Size

Output memory pool size.

### -field MotionVectorHeapMemoryPoolL0Size

Output memory pool size.

### -field MotionVectorHeapMemoryPoolL1Size
 
Output memory pool size.

## -remarks

## -see-also
