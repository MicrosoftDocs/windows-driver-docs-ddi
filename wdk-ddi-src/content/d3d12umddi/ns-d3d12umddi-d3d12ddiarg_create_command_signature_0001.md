---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001
title: D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001
author: windows-driver-content
description: Describes the parameters that the display driver uses to create a command signature.
tech.root: display
ms.assetid: bde7837f-15fc-4345-af92-40443a315682
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: struct
ms.keywords: D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001, D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001
product:
 - Windows
f1_keywords:
 - D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001
 - d3d12umddi/D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001
---

# D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001 structure


## -description

Describes the parameters that the display driver uses to create a command signature.

## -struct-fields

### -field ByteStride

Specifies the size of each argument of a command signature, in bytes.

### -field NumArgumentDescs

Specifies the number of arguments in the command signature.

### -field pArgumentDescs

An array of [**D3D12DDI_INDIRECT_ARGUMENT_DESC**](ns-d3d12umddi-d3d12ddi_indirect_argument_desc.md) structures, containing details of the arguments, including whether the argument is a vertex buffer, constant, constant buffer view, shader resource view, or unordered access view.

NodeMask

For single GPU operation, set this to zero. If there are multiple GPU nodes, set bits to identify the nodes (the device's physical adapters) for which the command signature is to apply. Each bit in the mask corresponds to a single node. Refer to Multi-adapter systems.

## -remarks

Use this structure with [**PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001**](nc-d3d12umddi-pfnd3d12ddi_create_command_signature_0001.md).

See the [Mesh Shader specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also

[**D3D12DDI_INDIRECT_ARGUMENT_DESC**](ns-d3d12umddi-d3d12ddi_indirect_argument_desc.md)

[**PFND3D12DDI_CREATE_COMMAND_SIGNATURE_0001**](nc-d3d12umddi-pfnd3d12ddi_create_command_signature_0001.md)

