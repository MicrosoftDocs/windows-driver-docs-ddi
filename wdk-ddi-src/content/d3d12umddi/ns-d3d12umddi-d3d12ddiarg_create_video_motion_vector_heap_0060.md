---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060
title: D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060
author: windows-driver-content
description: Arguments used to create a video motion vector heap.
tech.root: display
ms.assetid: ec111d01-4b9b-4944-bf67-52c704007084
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060 structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060, D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060,
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060
 - d3d12umddi/D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0060 structure


## -description

Arguments used to create a video motion vector heap.

## -struct-fields

### -field NodeMask

For a single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field InputFormat

The DXGI_FORMAT of the input and reference frames.

### -field BlockSize

The search block size to use with this motion vector heap.

### -field Precision

The precision of motion vector components.

### -field SizeRange

Indicates the minimum and maximum size of the inputs to the motion vector heap creation.

### -field hDrvProtectedResourceSession

Indicates the protected resource session to use for the motion vector heap creation.

## -remarks

## -see-also

