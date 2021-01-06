---
UID: NC:d3d12umddi.PFND3D12DDI_DISPATCH_MESH_0074
title: PFND3D12DDI_DISPATCH_MESH_0074 (d3d12umddi.h)
description: PFND3D12DDI_DISPATCH_MESH_0074 launches the threadgroups for the amplification shader, or for the mesh shader in a case where no amplification shader is attached.
ms.date: 03/24/2020
keywords: ["PFND3D12DDI_DISPATCH_MESH_0074 callback function"]
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
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3D12DDI_DISPATCH_MESH_0074
 - d3d12umddi/PFND3D12DDI_DISPATCH_MESH_0074
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DISPATCH_MESH_0074
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_DISPATCH_MESH_0074 callback function


## -description

**PFND3D12DDI_DISPATCH_MESH_0074** launches the thread groups for the amplification shader, or for the mesh shader in a case where no amplification shader is attached.

## -parameters

### -param Arg1

A handle to the command list.

### -param Arg2

Thread group count in X direction.

### -param Arg3

Thread group count in Y direction.

### -param Arg4

Thread group count in Z direction.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DISPATCH_MESH_0074 Pfnd3d12ddiDispatchMesh0074;

// Definition

VOID Pfnd3d12ddiDispatchMesh0074
(
    D3D12DDI_HCOMMANDLIST,
    UINT,
    UINT,
    UINT
)
{...}

```

## -remarks

See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also

