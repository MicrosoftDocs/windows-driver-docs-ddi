---
UID: NE:d3d12umddi.D3D12DDI_INDIRECT_ARGUMENT_TYPE
title: D3D12DDI_INDIRECT_ARGUMENT_TYPE
description: Specifies the type of the indirect parameter for indirect dispatch.
tech.root: display
ms.assetid: 6be46c04-3fc0-4761-9486-388c252d0684
ms.date: 03/24/2020
keywords: ["D3D12DDI_INDIRECT_ARGUMENT_TYPE enumeration"]
ms.keywords: D3D12DDI_INDIRECT_ARGUMENT_TYPE, D3D12DDI_INDIRECT_ARGUMENT_TYPE,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_INDIRECT_ARGUMENT_TYPE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - D3D12DDI_INDIRECT_ARGUMENT_TYPE
 - d3d12umddi/D3D12DDI_INDIRECT_ARGUMENT_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_INDIRECT_ARGUMENT_TYPE
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_INDIRECT_ARGUMENT_TYPE enumeration

## -description

Specifies the type of the indirect parameter for indirect dispatch.

## -enum-fields

### -field D3D12DDI_INDIRECT_ARGUMENT_TYPE_11_0

The driver supports Direct3D version 11 pipeline.

### -field D3D12_INDIRECT_ARGUMENT_TYPE_DRAW

Indicates the type is a Draw call.

### -field D3D12_INDIRECT_ARGUMENT_TYPE_DRAW_INDEXED

Indicates the type is a DrawIndexed call.

### -field D3D12_INDIRECT_ARGUMENT_TYPE_DISPATCH

Indicates the type is a Dispatch call.

### -field D3D12_INDIRECT_ARGUMENT_TYPE_VERTEX_BUFFER_VIEW

Indicates the type is a vertex buffer view.

### -field D3D12_INDIRECT_ARGUMENT_TYPE_INDEX_BUFFER_VIEW

Indicates the type is an index buffer view.

### -field D3D12_INDIRECT_ARGUMENT_TYPE_CONSTANT

Indicates the type is a constant.

### -field D3D12_INDIRECT_ARGUMENT_TYPE_CONSTANT_BUFFER_VIEW

Indicates the type is a constant buffer view (CBV).

### -field D3D12_INDIRECT_ARGUMENT_TYPE_SHADER_RESOURCE_VIEW

Indicates the type is a shader resource view (SRV).

### -field D3D12_INDIRECT_ARGUMENT_TYPE_UNORDERED_ACCESS_VIEW

Indicates the type is an unordered access view (UAV).

### -field D3D12DDI_INDIRECT_ARGUMENT_TYPE_DISPATCH_RAYS

Indicates the type is a DispatchRays call. Available starting with Windows 10, version 2004.

### -field D3D12DDI_INDIRECT_ARGUMENT_TYPE_DISPATCH_MESH

Indicates the type is a DispatchMesh call. Available starting with Windows 10, version 2004.

## -remarks

**D3D12DDI_INDIRECT_ARGUMENT_TYPE** is a member of [**D3D12DDI_INDIRECT_ARGUMENT_DESC**](ns-d3d12umddi-d3d12ddi_indirect_argument_desc.md).

See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also

[**D3D12DDI_INDIRECT_ARGUMENT_DESC**](ns-d3d12umddi-d3d12ddi_indirect_argument_desc.md)
