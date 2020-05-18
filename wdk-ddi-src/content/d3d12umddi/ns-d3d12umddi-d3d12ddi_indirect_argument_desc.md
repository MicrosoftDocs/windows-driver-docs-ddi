---
UID: NS:d3d12umddi.D3D12DDI_INDIRECT_ARGUMENT_DESC
title: D3D12DDI_INDIRECT_ARGUMENT_DESC (d3d12umddi.h)
description: Describes an indirect argument (an indirect parameter), for use with a command signature.
old-location: display\d3d12ddi_INDIRECT_ARGUMENT_DESC.htm
ms.assetid: 3946483d-85a2-4f2f-9937-894cbe4e4184
ms.date: 03/24/2020
keywords: ["D3D12DDI_INDIRECT_ARGUMENT_DESC structure"]
ms.keywords: D3D12DDI_INDIRECT_ARGUMENT_DESC, D3D12DDI_INDIRECT_ARGUMENT_DESC structure [Display Devices], d3d12umddi/D3D12DDI_INDIRECT_ARGUMENT_DESC, display.d3d12ddi_INDIRECT_ARGUMENT_DESC
f1_keywords:
 - "d3d12umddi/D3D12DDI_INDIRECT_ARGUMENT_DESC"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_INDIRECT_ARGUMENT_DESC
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_INDIRECT_ARGUMENT_DESC
---

# D3D12DDI_INDIRECT_ARGUMENT_DESC structure

## -description

Describes an indirect argument (an indirect parameter), for use with a command signature.

## -struct-fields

### -field Type

A single D3D12DDI_INDIRECT_ARGUMENT_TYPE enumeration constant.

### -field VertexBuffer

### -field VertexBuffer.Slot

Specifies the slot containing the vertex buffer address.

### -field Constant

### -field Constant.RootParameterIndex

Specifies the root index of the constant.

### -field Constant.DestOffsetIn32BitValues

The offset, in 32-bit values, to set the first constant of the group. Supports multi-value constants at a given root index. Root constant entries must be sorted from smallest to largest **DestOffsetIn32BitValues**.

### -field Constant.Num32BitValuesToSet

The number of 32-bit constants that are set at the given root index. Supports multi-value constants at a given root index.

### -field ConstantBufferView

### -field ConstantBufferView.RootParameterIndex

Specifies the root index of the CBV.

### -field ShaderResourceView

### -field ShaderResourceView.RootParameterIndex

Specifies the root index of the SRV.

### -field UnorderedAccessView

### -field UnorderedAccessView.RootParameterIndex

Specifies the root index of the UAV.

## -remarks

Use this structure with the [**D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001**] structure.

See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also
