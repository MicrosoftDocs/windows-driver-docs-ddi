---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0063
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0063
description: The device functions of video, used in D3D12DDI_FEATURE_VERSION_VIDEO_0063.
tech.root: display
ms.date: 04/04/2019
keywords: ["D3D12DDI_DEVICE_FUNCS_VIDEO_0063 structure"]
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0063, D3D12DDI_DEVICE_FUNCS_VIDEO_0063,
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
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0063
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - D3D12DDI_DEVICE_FUNCS_VIDEO_0063
 - d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0063
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEVICE_FUNCS_VIDEO_0063
dev_langs:
 - c++
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0063 structure


## -description

The device functions of video, used in D3D12DDI_FEATURE_VERSION_VIDEO_0063.

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

### -field pfnCalcPrivateVideoExtensionCommandSize

Returns the driver for the video extension object size.

### -field pfnCreateVideoExtensionCommand

Creates a video extension command.

### -field pfnDestroyVideoExtensionCommand

 
Destroys the video extension command.

## -remarks

## -see-also

