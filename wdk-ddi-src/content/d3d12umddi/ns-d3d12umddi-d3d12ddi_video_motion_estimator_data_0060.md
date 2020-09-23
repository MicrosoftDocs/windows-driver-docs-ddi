---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060
title: D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060
description: The video capability check for motion estimation.
tech.root: display
ms.assetid: e7494c78-bd0b-4da1-bf73-c88519454686
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060 structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060, D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060
 - d3d12umddi/D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0060 structure


## -description

The video capability check for motion estimation.

## -struct-fields

### -field NodeIndex

In multi-adapter operation, this value indicates which physical adapter of the device this operation applies to.

### -field InputFormat

The DXGI_FORMAT of the input frame and reference frame. Currently only DXGI_FORMAT_NV12 is allowed.

### -field BlockSizeFlags

The block sizes supported by driver. At least one bit must be set to support the motion estimation operation. Set this value to NONE if not supported. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_SEARCH_BLOCK_SIZE_FLAGS_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_search_block_size_flags_0053.md).

### -field PrecisionFlags

The precision supported by driver. At least one bit must be set to support the motion estimation operation. Set this value to NONE if not supported. See [D3D12DDI_VIDEO_MOTION_ESTIMATOR_VECTOR_PRECISION_FLAGS_0053](ne-d3d12umddi-d3d12ddi_video_motion_estimator_vector_precision_flags_0053.md).

### -field SizeRange

 
Sets the minimum and maximum input and reference size in Pixels supported by driver. Set this value to zeros when motion estimation is not supported.

## -remarks

## -see-also

