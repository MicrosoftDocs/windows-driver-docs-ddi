---
UID: NS:d3d12umddi.D3D12DDIARG_ADD_TO_STATE_OBJECT_0072
title: D3D12DDIARG_ADD_TO_STATE_OBJECT_0072
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: ec8278a7-8c50-4d20-b03c-6648ca8752b7
tech.root: display
description: Structure used to add subobject(s) to a state object.
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
req.typenames: D3D12DDIARG_ADD_TO_STATE_OBJECT_0072
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_ADD_TO_STATE_OBJECT_0072
f1_keywords:
 - d3d12umddi/D3D12DDIARG_ADD_TO_STATE_OBJECT_0072
dev_langs:
 - c++
---

## -description

Structure used to add subobject(s) to a state object.

## -struct-fields

### -field Type

A [**D3D12DDI_STATE_OBJECT_TYPE**](ne-d3d12umddi-d3d12ddi_state_object_type.md) value indicating the type of GPU pipeline the state object is to be used with.

### -field NumSubobjects

Number of subobjects in **pSubobjects**.

### -field pSubobjects

Array of [**D3D12DDI_STATE_SUBOBJECT_0054**](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md) structures.

### -field StateObjectToGrowFrom

Handle to the state object to grow from.

## -remarks

See the [DirectX RayTracing (DXR) Specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12DDI_STATE_OBJECT_TYPE**](ne-d3d12umddi-d3d12ddi_state_object_type.md)

[**D3D12DDI_STATE_SUBOBJECT_0054**](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md)
