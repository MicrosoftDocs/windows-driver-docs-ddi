---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOPROCESSOR_0072
title: PFND3D12DDI_CREATEVIDEOPROCESSOR_0072 (d3d12umddi.h)
description: Used to create a video processor.
ms.assetid: e276c837-8472-4975-afb5-35a5cbcae32a
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CREATEVIDEOPROCESSOR_0072 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEVIDEOPROCESSOR_0072"
 - "PFND3D12DDI_CREATEVIDEOPROCESSOR_0072"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEVIDEOPROCESSOR_0072
product:
 - Windows
---

# PFND3D12DDI_CREATEVIDEOPROCESSOR_0072 callback function

## -description

The *pfnCreateVideoProcessor* callback function creates a video processor.

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context).

### -param pArgs

A [**D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_processor_0072.md) structure with arguments used to create a video processor.

### -param hDrvVideoProcessor

The video processor.

## -returns

Returns STATUS_SUCCESS if completed successfully.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEVIDEOPROCESSOR_0072 Pfnd3d12ddiCreatevideoprocessor0072;

// Definition

HRESULT Pfnd3d12ddiCreatevideoprocessor0072
(
    D3D12DDI_HDEVICE hDrvDevice
    CONST D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072 *pArgs
    D3D12DDI_HVIDEOPROCESSOR_0020 hDrvVideoProcessor
)
{...}

PFND3D12DDI_CREATEVIDEOPROCESSOR_0072

```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_processor_0072.md) and then calling Pfnd3d12ddiCreatevideoprocessor0072.

See the [D3D Video Protected Resource Support Specification](https://microsoft.github.io/DirectX-Specs/d3d/D3D12_Video_ProtectedResourceSupport.html) for more information.

## -see-also

[**D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072**](ns-d3d12umddi-d3d12ddiarg_create_video_processor_0072.md)
