---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_SHADER_0026
title: D3D12DDIARG_CREATE_SHADER_0026
author: windows-driver-content
description: Describes the parameters that the display driver uses to create a shader.
tech.root: display
ms.assetid: 0806447d-f18e-455b-b5d5-40bb21ff50f6
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: struct
ms.keywords: D3D12DDIARG_CREATE_SHADER_0026, D3D12DDIARG_CREATE_SHADER_0026, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDIARG_CREATE_SHADER_0026
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDIARG_CREATE_SHADER_0026
product: 
 - Windows
targetos: Windows
---

# D3D12DDIARG_CREATE_SHADER_0026 structure

## -description

Describes the parameters that the display driver uses to create a shader.

## -struct-fields

### -field hRootSignature

Handle to a root signature.

### -field pShaderCode

Pointer to the shader code.

### -field IOSignatures

IO signature.

### -field IOSignatures.Standard

Pointer to a D3D12DDIARG_STAGE_IO_SIGNATURES structure.

### -field IOSignatures.Tessellation

Pointer to a D3D12DDIARG_TESSELLATION_IO_SIGNATURES structure.

### -field Flags

A [**D3D12DDI_CREATE_SHADER_FLAGS**](ne-d3d12umddi-d3d12ddi_create_shader_flags.md) value specifying the flags for shader creation.

### -field LibraryReference

A [**D3D12DDI_LIBRARY_REFERENCE_0010**](ns-d3d12umddi-d3d12ddi_library_reference_0010.md) structure describing a pipeline library.

### -field ShaderCodeHash

A [**D3D12DDI_SHADERCACHE_HASH**](ns-d3d12umddi-d3d12ddi_shadercache_hash.md) structure containing a hash value.

## -remarks

See the [Mesh Shader specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also

[**D3D12DDI_CREATE_SHADER_FLAGS**](ne-d3d12umddi-d3d12ddi_create_shader_flags.md)

[**D3D12DDI_LIBRARY_REFERENCE_0010**](ns-d3d12umddi-d3d12ddi_library_reference_0010.md)

[**D3D12DDI_SHADERCACHE_HASH**](ns-d3d12umddi-d3d12ddi_shadercache_hash.md)
