---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053
title: D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053 (d3d12umddi.h)
description: The video capability check for motion estimation.
ms.assetid: a41a54fa-b634-4bc5-a499-bf7af9598bf9
ms.date: 10/19/2018
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053"
ms.keywords: D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053, D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053, 
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
req.typenames: D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053 structure

## -description

The video capability check for motion estimation.

## -struct-fields

### -field NodeIndex

In multi-adapter operation, this value indicates which physical adapter of the device this operation applies to.

### -field InputFormat

The DXGI_FORMAT of the input frame and reference frame. Currently only DXGI_FORMAT_NV12 is allowed.

### -field BlockSizeFlags

The block sizes supported by driver. At least one bit must be set to support the motion estimation operation. Set this value to NONE if not supported.  See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SEARCH_BLOCK_SIZE_FLAGS_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_search_block_size_flags_0053.md).

### -field PrecisionFlags

The precision supported by driver. At least one bit must be set to support the motion estimation operation. Set this value to NONE if not supported.  See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_VECTOR_PRECISION_FLAGS_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_vector_precision_flags_0053.md).

### -field DifferencesMetricFlags

Sets the optional differences metrics supported by hardware. The motion search operation can still be supported with this set to NONE. Set this value to NONE if motion estimation is not supported. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_DIFFERENCES_METRIC_FLAGS_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_differences_metric_flags_0053.md)

### -field SizeRange
 
Sets the minimum and maximum input and reference size in Pixels supported by driver. Set this value to zeros when motion estimation is not supported.

## -remarks

## -see-also
