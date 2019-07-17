---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060
title: D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060
author: windows-driver-content
description: Specifies the creation arguments for the video motion estimator.
tech.root: display
ms.assetid: 0529922e-06be-4cc7-85e5-fa2158fd95cc
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060, D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060, 
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060
product: 
 - Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0060 structure

## -description

Specifies the creation arguments for the video motion estimator.

## -struct-fields

### -field NodeMask

For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field InputFormat

The DXGI_FORMAT of the input and reference frames. This motion estimator may only be used with input textures of this format.

### -field BlockSize

The search block size to use with this motion estimator. This parameter determines the number of motion vectors and difference metrics output during the resolve step. This must be a block size reported as supported by the driver.

### -field Precision

The precision of motion vector components. This must be a precision reported as supported by the driver.

### -field SizeRange

Indicates the minimum and maximum size of the inputs to the motion estimation operation. Actual size is provided at motion estimation time. Driver should allocate at the creation of the motion estimator to support any size within the range. This size range must be a subset of the size range supported by the driver.

### -field hDrvProtectedResourceSession
 
Indicates the protected resource session to use for the motion estimator. This can inform internal allocations for the motion estimator. This value is NULL if the motion estimator will operate on unprotected resources.

## -remarks

## -see-also
