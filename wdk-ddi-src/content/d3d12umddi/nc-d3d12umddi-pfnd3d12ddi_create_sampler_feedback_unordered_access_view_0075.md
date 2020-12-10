---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075
title: PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075 (d3d12umddi.h)
description: Used to create a sampler feedback with unordered access view.
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075 callback function"]
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
ms.custom: 
f1_keywords:
 - PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075
 - d3d12umddi/PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075 callback function


## -description

Used to create a sampler feedback with unordered access view.

## -parameters

### -param hDrvDevice

[in] A handle to the display device (graphics context).

### -param hDrvTargetedResource

[in] Handle to targeted resource.

### -param hDrvFeedbackResource

[in] Handle to feedback resource.

### -param DestDescriptor

[in] A [D3D12DDI_CPU_DESCRIPTOR_HANDLE](ns-d3d12umddi-d3d12ddi_cpu_descriptor_handle.md) structure that defines the destination target.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075 Pfnd3d12ddiCreateSamplerFeedbackUnorderedAccessView0075;

// Definition

VOID Pfnd3d12ddiCreateSamplerFeedbackUnorderedAccessView0075
(
    D3D12DDI_HDEVICE hDrvDevice,
    D3D12DDI_HRESOURCE hDrvTargetedResource,
    D3D12DDI_HRESOURCE hDrvFeedbackResource,
    D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_SAMPLER_FEEDBACK_UNORDERED_ACCESS_VIEW_0075


```

## -remarks

See the [D3D Sampler Feedback Specification](https://microsoft.github.io/DirectX-Specs/d3d/SamplerFeedback.html) for more information.

## -see-also

[D3D12DDI_CPU_DESCRIPTOR_HANDLE](ns-d3d12umddi-d3d12ddi_cpu_descriptor_handle.md)

