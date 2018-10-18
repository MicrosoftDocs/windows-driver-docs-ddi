---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0053
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0053
author: windows-driver-content
description: The device functions of video.
ms.assetid: d32a1690-546d-4c00-b30c-7646ced2117d
ms.date: 
ms.topic: struct
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0053, D3D12DDI_DEVICE_FUNCS_VIDEO_0053, 
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
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0053
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0053
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0053 structure

## -description

The device functions of video.

## -struct-fields

### -field pfnGetCaps

Get capabilities. 


### -field pfnCalcPrivateVideoDecoderSize

Calculates the private video decoder size. 


### -field pfnCreateVideoDecoder

Creates a video decoder. 


### -field pfnDestroyVideoDecoder

Destroys the video decoder. 


### -field pfnCalcPrivateVideoDecoderHeapSize

Calculates the private video decoder heap size. 


### -field pfnCreateVideoDecoderHeap

Creates the video decoder heap. 


### -field pfnDestroyVideoDecoderHeap

Destroys the video decoder heap. 


### -field pfnCalcPrivateVideoProcessorSize

Calculates the private video processor size. 


### -field pfnCreateVideoProcessor

Creates the video processor. 


### -field pfnDestroyVideoProcessor

Destroys the video processor. 
 
### -field pfnCalcPrivateVideoMotionEstimatorSize

Calculates private video motion estimator size.

### -field pfnCreateVideoMotionEstimator

Create video motion estimator.

### -field pfnDestroyVideoMotionEstimator

Destroy video motion estimator.

### -field pfnCalcPrivateVideoMotionVectorHeapSize

Calculate private video motion vector heap size.

### -field pfnCreateVideoMotionVectorHeap

Create video motion vector heap.

### -field pfnDestroyVideoMotionVectorHeap

Destroy video motion vector heap.

## -remarks

## -see-also
