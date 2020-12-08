---
UID: NS:d3d12umddi.D3D12DDI_DISPATCH_MESH_ARGUMENTS
title: D3D12DDI_DISPATCH_MESH_ARGUMENTS
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
tech.root: display
description: Mesh shader threadgroups.
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
req.typenames: D3D12DDI_DISPATCH_MESH_ARGUMENTS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DISPATCH_MESH_ARGUMENTS
f1_keywords:
 - D3D12DDI_DISPATCH_MESH_ARGUMENTS
 - d3d12umddi/D3D12DDI_DISPATCH_MESH_ARGUMENTS
dev_langs:
 - c++
---

## -description

Mesh shader threadgroups.

## -struct-fields

### -field ThreadGroupCountX

Thread group count in the X direction.

### -field ThreadGroupCountY

Thread group count in the Y direction.

### -field ThreadGroupCountZ

Tread group count in the Z direction.

## -remarks

The total number of threads is **ThreadGroupCountX * ThreadGroupCountY * ThreadGroupCountZ**.

See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also

