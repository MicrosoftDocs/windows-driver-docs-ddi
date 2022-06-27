---
UID: NE:d3d12umddi.D3D12DDI_ROOT_SIGNATURE_FLAGS
title: D3D12DDI_ROOT_SIGNATURE_FLAGS (d3d12umddi.h)
description: Specifies options for root signature layout.
ms.date: 05/24/2022
keywords: ["D3D12DDI_ROOT_SIGNATURE_FLAGS enumeration"]
ms.keywords: D3D12DDI_ROOT_SIGNATURE_FLAGS, D3D12DDI_ROOT_SIGNATURE_FLAGS,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_ROOT_SIGNATURE_FLAGS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - D3D12DDI_ROOT_SIGNATURE_FLAGS
 - d3d12umddi/D3D12DDI_ROOT_SIGNATURE_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_ROOT_SIGNATURE_FLAGS
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_ROOT_SIGNATURE_FLAGS enumeration

## -description

Specifies options for root signature layout.

## -enum-fields

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_NONE:0x0

Indicates default behavior.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_ALLOW_INPUT_ASSEMBLER_INPUT_LAYOUT:0x1

The app is opting in to using the Input Assembler (requiring an input layout that defines a set of vertex buffer bindings). Omitting this flag can result in one root argument space being saved on some hardware. Omit this flag if the Input Assembler is not required, though the optimization is minor.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_DENY_VERTEX_SHADER_ROOT_ACCESS:0x2

Denies the vertex shader access to the root signature.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_DENY_HULL_SHADER_ROOT_ACCESS:0x4

Denies the hull shader access to the root signature.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_DENY_DOMAIN_SHADER_ROOT_ACCESS:0x8

Denies the domain shader access to the root signature.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_DENY_GEOMETRY_SHADER_ROOT_ACCESS:0x10

Denies the geometry shader access to the root signature.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_DENY_PIXEL_SHADER_ROOT_ACCESS:0x20

Denies the pixel shader access to the root signature.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_ALLOW_STREAM_OUTPUT:0x40

The root signature allows stream output.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_LOCAL_ROOT_SIGNATURE:0x80

The local root signature is supported.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_DENY_AMPLIFICATION_SHADER_ROOT_ACCESS:0x100

Denies the amplification shader access to the root signature. Available starting with Windows 10, version 2004. See the [Mesh Shader specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information about amplification shaders.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_DENY_MESH_SHADER_ROOT_ACCESS:0x200

Denies the mesh shader access to the root signature. Available starting with Windows 10, version 2004. See the [Mesh Shader specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information about mesh shaders.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_CBV_SRV_UAV_HEAP_DIRECTLY_INDEXED:0x400

Shaders are allowed to index the CBV/SRV/UAV descriptor heap directly.

### -field D3D12DDI_ROOT_SIGNATURE_FLAG_SAMPLER_HEAP_DIRECTLY_INDEXED:0x800

Shaders are allowed to index the sampler descriptor heap directly.

## -remarks

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.
