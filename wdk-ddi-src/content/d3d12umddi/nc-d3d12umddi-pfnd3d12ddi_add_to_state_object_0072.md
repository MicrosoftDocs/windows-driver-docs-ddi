---
UID: NC:d3d12umddi.PFND3D12DDI_ADD_TO_STATE_OBJECT_0072
title: PFND3D12DDI_ADD_TO_STATE_OBJECT_0072 (d3d12umddi.h)
description: PFND3D12DDI_ADD_TO_STATE_OBJECT_0072 incrementally adds to an existing state object.
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_ADD_TO_STATE_OBJECT_0072 callback function"]
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
 - PFND3D12DDI_ADD_TO_STATE_OBJECT_0072
 - d3d12umddi/PFND3D12DDI_ADD_TO_STATE_OBJECT_0072
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_ADD_TO_STATE_OBJECT_0072
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_ADD_TO_STATE_OBJECT_0072 callback function


## -description

**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072** incrementally adds to an existing state object.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

[in] Pointer to a [**D3D12DDIARG_ADD_TO_STATE_OBJECT_0072**] structure containing subobject(s) to add to a state object.

### -param Arg3

Handle to a state object.

### -param Arg4

Handle to a runtime handle type state object.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_ADD_TO_STATE_OBJECT_0072 Pfnd3d12ddiAddToStateObject0072;

// Definition

HRESULT Pfnd3d12ddiAddToStateObject0072
(
    D3D12DDI_HDEVICE Arg1,
    D3D12DDIARG_ADD_TO_STATE_OBJECT_0072 *Arg2,
    D3D12DDI_HSTATEOBJECT_0054 Arg3,
    D3D12DDI_HRTSTATEOBJECT_0054 Arg4
)
{...}

```

## -remarks

A state object is created via [**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md).

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12DDIARG_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)

[**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md)

