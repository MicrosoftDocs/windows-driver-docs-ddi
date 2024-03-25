---
UID: NE:d3d12umddi.D3D12DDI_SHADER_VISIBILITY
title: D3D12DDI_SHADER_VISIBILITY
description: Specifies the shaders that can access the contents of a given root signature slot.
tech.root: display
ms.date: 05/24/2022
ms.keywords: D3D12DDI_SHADER_VISIBILITY, D3D12DDI_SHADER_VISIBILITY,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_SHADER_VISIBILITY
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_SHADER_VISIBILITY
f1_keywords:
 - D3D12DDI_SHADER_VISIBILITY
 - d3d12umddi/D3D12DDI_SHADER_VISIBILITY
---

# D3D12DDI_SHADER_VISIBILITY enumeration

## -description

**D3D12DDI_SHADER_VISIBILITY** identifies the shaders that can access the contents of a given root signature slot.

## -enum-fields

### -field D3D12DDI_SHADER_VISIBILITY_ALL:0

All shader stages can access whatever is bound at the root signature slot.

### -field D3D12DDI_SHADER_VISIBILITY_VERTEX:1

The vertex shader stage can access whatever is bound at the root signature slot.

### -field D3D12DDI_SHADER_VISIBILITY_HULL:2

The hull shader stage can access whatever is bound at the root signature slot.

### -field D3D12DDI_SHADER_VISIBILITY_DOMAIN:3

The domain shader stage can access whatever is bound at the root signature slot.

### -field D3D12DDI_SHADER_VISIBILITY_GEOMETRY:4

The geometry shader stage can access whatever is bound at the root signature slot.

### -field D3D12DDI_SHADER_VISIBILITY_PIXEL:5

The pixel shader stage can access whatever is bound at the root signature slot.

### -field D3D12DDI_SHADER_VISIBILITY_AMPLIFICATION:6

The amplification shader stage can access whatever is bound at the root signature slot.

### -field D3D12DDI_SHADER_VISIBILITY_MESH:7

The mesh shader stage can access whatever is bound at the root signature slot.

## -remarks

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.
