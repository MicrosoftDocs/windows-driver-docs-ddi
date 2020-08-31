---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072
title: PFND3D12DDI_PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072 (d3d12umddi.h)
description: PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072 calculates the size of the state object.
ms.assetid: d95f0900-e252-48c1-9846-00bd8973e3c7
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072 callback function"]
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
 - PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072
 - d3d12umddi/PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072
product:
 - Windows
---

# PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072 callback function


## -description

**PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072** calculates the size of the state object.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

[in] Pointer to a [**D3D12DDIARG_ADD_TO_STATE_OBJECT_0072**](ns-d3d12umddi-d3d12ddiarg_add_to_state_object_0072.md) structure.

## -returns

Returns the size of the state object in bytes.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072 Pfnd3d12ddiCalcPrivateAddToStateObjectSize0072;

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateAddToStateObjectSize0072
(
    D3D12DDI_HDEVICE,
    CONST D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072*
)
{...}

PFND3D12DDI_CALC_PRIVATE_ADD_TO_STATE_OBJECT_SIZE_0072

```

## -remarks

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12DDIARG_ADD_TO_STATE_OBJECT_0072**](ns-d3d12umddi-d3d12ddiarg_add_to_state_object_0072.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)

