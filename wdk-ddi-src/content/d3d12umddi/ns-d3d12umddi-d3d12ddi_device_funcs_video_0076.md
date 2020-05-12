---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0076
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0076
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: f2ea1b98-b424-4ee5-84dd-9ffbe5122483
tech.root: display
description: Contains device functions for core features in video, used in D3D12DDI_FEATURE_VERSION_VIDEO_0076.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0076
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEVICE_FUNCS_VIDEO_0076
f1_keywords:
 - d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0076
dev_langs:
 - c++
---

## -description

Contains device functions for core features in video, used in D3D12DDI_FEATURE_VERSION_VIDEO_0076.

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

### -field pfnExecuteDeviceVideoExtensionCommand

Executes a device video extension command. See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -remarks

## -see-also
