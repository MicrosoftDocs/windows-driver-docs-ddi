---
UID: NS:d3d12umddi.D3D12DDIARG_MESH_IO_SIGNATURES
title: D3D12DDIARG_MESH_IO_SIGNATURES
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: dc26c4a7-52b6-4325-9033-c516dfb38315
tech.root: display
description: The D3D12DDIARG_MESH_IO_SIGNATURES structure describes a set of signatures for a given mesh shader's output primitives and vertices.
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
req.typenames: D3D12DDIARG_MESH_IO_SIGNATURES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_MESH_IO_SIGNATURES
f1_keywords:
 - d3d12umddi/D3D12DDIARG_MESH_IO_SIGNATURES
 - ""
dev_langs:
 - c++
---

## -description

The **D3D12DDIARG_MESH_IO_SIGNATURES** structure describes a set of signatures for a given mesh shader's output primitives and vertices.

## -struct-fields

### -field pPrimitiveOutputSignature

An array of signatures; namely, the set of all registers affected by primitives output by the mesh shader.

### -field NumPrimitiveOutputSignatureEntries

Size, in elements, of the **pPrimitiveOutputSignature** array.

### -field pVertexOutputSignature

An array of signatures; namely, the union of all registers affected by vertices output by the mesh shader.

### -field NumVertexOutputSignatureEntries

Size, in elements, of the **pVertexOutputSignature** array.

## -remarks

This information is passed to the driver on creation of a mesh shader.

See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also
