---
UID: NS:d3d12umddi.D3D12DDI_INDIRECT_ARGUMENT_DESC
title: D3D12DDI_INDIRECT_ARGUMENT_DESC (d3d12umddi.h)
description: Describes an indirect argument (an indirect parameter), for use with a command signature.
old-location: display\d3d12ddi_INDIRECT_ARGUMENT_DESC.htm
ms.date: 05/20/2020
keywords: ["D3D12DDI_INDIRECT_ARGUMENT_DESC structure"]
ms.keywords: D3D12DDI_INDIRECT_ARGUMENT_DESC, D3D12DDI_INDIRECT_ARGUMENT_DESC structure [Display Devices], d3d12umddi/D3D12DDI_INDIRECT_ARGUMENT_DESC, display.d3d12ddi_INDIRECT_ARGUMENT_DESC
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_INDIRECT_ARGUMENT_DESC
f1_keywords:
 - D3D12DDI_INDIRECT_ARGUMENT_DESC
 - d3d12umddi/D3D12DDI_INDIRECT_ARGUMENT_DESC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_INDIRECT_ARGUMENT_DESC
---

# D3D12DDI_INDIRECT_ARGUMENT_DESC structure

## -description

The **D3D12DDI_INDIRECT_ARGUMENT_DESC** structure describes an indirect argument (an indirect parameter), for use with a command signature.

## -struct-fields

### -field Type

A [**D3D12DDI_INDIRECT_ARGUMENT_TYPE**](ne-d3d12umddi-d3d12ddi_indirect_argument_type.md) enumeration value that specifies the type of indirect argument. This value determines which member of the union is used.

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

### -field IncrementingConstant

### -field IncrementingConstant.RootParameterIndex

The index within the root signature that identifies the root constant to be updated.

### -field IncrementingConstant.DestOffsetIn32BitValues

This field specifies the offset, in terms of 32-bit values (not bytes), within the root constant's memory where the incremented value will be written. It defines the position within the root constant at which the incrementing constant will start. If the root constant is an array of multiple 32-bit values, this offset indicates which element of the array will receive the first incremented value.

## -remarks

Indirect arguments are used in conjunction with command signatures to specify the type and structure of data that the GPU will read from a buffer to execute a command, without the CPU needing to be involved in each individual draw or dispatch call.

Use this structure with the [**D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001**](ns-d3d12umddi-d3d12ddiarg_create_command_signature_0001.md) structure.

See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -see-also

[**D3D12DDI_INDIRECT_ARGUMENT_TYPE**](ne-d3d12umddi-d3d12ddi_indirect_argument_type.md)

[**D3D12DDIARG_CREATE_COMMAND_SIGNATURE_0001**](ns-d3d12umddi-d3d12ddiarg_create_command_signature_0001.md)
