---
UID: NE:d3d12umddi.D3D12DDI_MESH_SHADER_TIER
title: D3D12DDI_MESH_SHADER_TIER
ms.date: 09/22/2022
targetos: Windows
tech.root: display
description: D3D12DDI_MESH_SHADER_TIER specifies the mesh shader tier.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_MESH_SHADER_TIER
f1_keywords:
 - D3D12DDI_MESH_SHADER_TIER
 - d3d12umddi/D3D12DDI_MESH_SHADER_TIER
dev_langs:
 - c++
---

## -description

**D3D12DDI_MESH_SHADER_TIER** specifies the mesh shader tier.

## -enum-fields

### -field D3D12DDI_MESH_SHADER_TIER_NOT_SUPPORTED:0

Mesh shading is not supported.

### -field D3D12DDI_MESH_SHADER_TIER_1:10

The device supports mesh shader tier 1.

## -remarks

See [**D3D12_MESH_SHADER_TIER**](/windows/win32/api/d3d12/ne-d3d12-d3d12_mesh_shader_tier) for more information about the tiers.

See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0089**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0073.md)
