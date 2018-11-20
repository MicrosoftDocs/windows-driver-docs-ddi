---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053
title: D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053
author: windows-driver-content
description: Arguments used by the PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0053 callback function to create a motion vector heap.
ms.assetid: 40b498a6-4166-4f45-87dc-3e559a0821c7
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053, D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053, 
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053 structure

## -description

Arguments used by the [PFND3D12DDI_CREATEVIDEOMOTIONVECTORHEAP_0053](nc-d3d12umddi-pfnd3d12ddi_createvideomotionvectorheap_0053.md) callback function to create a motion vector heap. 

## -struct-fields

### -field NodeMask

For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field InputFormat

The DXGI_FORMAT of the input and reference frames.

### -field BlockSize

The search block size to use with this motion vector heap.

### -field Precision

The precision of motion vector components.

### -field DifferencesMetric

Indicates the differences metric to capture during motion vector heap creation.

### -field SizeRange

Indicates the minimum and maximum size of the inputs to the motion vector heap creation.

### -field hDrvProtectedResourceSession
 
Indicates the protected resource session to use for the motion vector heap creation.

## -remarks

## -see-also
