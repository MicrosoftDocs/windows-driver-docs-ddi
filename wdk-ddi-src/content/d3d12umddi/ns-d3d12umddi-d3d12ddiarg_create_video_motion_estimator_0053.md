---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053
title: D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053
description: Specifies the creation arguments for the motion estimator.
ms.assetid: 0d46a722-c3ad-4e95-a4a0-3d0fc9dc0dfb
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053, D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053, 
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053 structure

## -description

Specifies the creation arguments for the motion estimator. 

## -struct-fields

### -field NodeMask

For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field InputFormat

The DXGI_FORMAT of the input and reference frames. This motion estimator may only be used with input textures of this format.

### -field BlockSize

The search block size to use with this motion estimator. This parameter determines the number of motion vectors and difference metrics output during the resolve step. This must be a block size reported as supported by the driver. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SEARCH_BLOCK_SIZE_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_search_block_size_0053.md).

### -field Precision

The precision of motion vector components.  This must be a precision reported as supported by the driver. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_VECTOR_PRECISION_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_vector_precision_0053.md).

### -field DifferencesMetric

Indicates the differences metric to capture during motion estimation. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_DIFFERENCES_METRIC_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_differences_metric_0053.md).

### -field SizeRange

Indicates the minimum and maximum size of the inputs to the motion estimation operation. Actual size is provided at motion estimation time.  Driver should allocate at the creation of the motion estimator to support any size within the range. This size range must be a subset of the size range supported by the driver. See [D3D12DDI_VIDEO_SIZE_RANGE_0032](ns-d3d12umddi-d3d12ddi_video_size_range_0032.md)

### -field hDrvProtectedResourceSession
 
Indicates the protected resource session to use for the motion estimator. This can inform internal allocations for the motion estimator. This value is NULL if the motion estimator will operate on unprotected resources.

## -remarks

Valid arguments are determined by the **D3D12DDICAPS_TYPE_VIDEO_0053_MOTION_ESTIMATOR** capability check of the [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) enumeration.

## -see-also
