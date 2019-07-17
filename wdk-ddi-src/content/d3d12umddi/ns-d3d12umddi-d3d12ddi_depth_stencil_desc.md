---
UID: NS:d3d12umddi.D3D12DDI_DEPTH_STENCIL_DESC
title: D3D12DDI_DEPTH_STENCIL_DESC (d3d12umddi.h)
description: The D3D12DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.
ms.assetid: a894e69c-692b-4783-8265-14eae56c9264
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_DEPTH_STENCIL_DESC"
ms.keywords: D3D12DDI_DEPTH_STENCIL_DESC, D3D12DDI_DEPTH_STENCIL_DESC, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_DEPTH_STENCIL_DESC
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_DEPTH_STENCIL_DESC
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_DEPTH_STENCIL_DESC structure

## -description

The D3D12DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.

## -struct-fields

### -field DepthEnable

A Boolean value that specifies whether depth is enabled. TRUE indicates depth is enabled; FALSE indicates depth is disabled. 

### -field DepthWriteMask

A bitwise value that indicates the write properties for a depth stencil state. This member is a valid bitwise OR of the following values from the [D3D12DDI_DEPTH_WRITE_MASK](ne-d3d12umddi-d3d12ddi_depth_write_mask.md) enumeration.

### -field DepthFunc

A [D3D12DDI_COMPARISON_FUNC](ne-d3d12umddi-d3d12ddi_comparison_func.md)-typed value that indicates the depth-comparison function to perform.

### -field StencilEnable

A Boolean value that specifies whether stencil is enabled. TRUE indicates stencil is enabled; FALSE indicates stencil is disabled. 

### -field FrontEnable

A Boolean value that specifies whether the performance of stencil operations on forward-facing polygons is enabled. TRUE indicates that the performance on forward-facing polygons is enabled; FALSE indicates that it is disabled. 

### -field BackEnable

A Boolean value that specifies whether the performance of stencil operations on back-facing polygons is enabled. TRUE indicates that the performance on back-facing polygons is enabled; FALSE indicates that it is disabled. 

### -field StencilReadMask

An 8-bit bitwise value that the driver uses in a bitwise AND operation with the stencil value in the stencil buffer immediately after reading the stencil value out of the stencil buffer.

### -field StencilWriteMask

An 8-bit bitwise value that the driver uses in a bitwise AND operation with the current stencil value before writing the result back out to the stencil buffer.

### -field FrontFace

A [D3D12DDI_DEPTH_STENCILOP_DESC](ns-d3d12umddi-d3d12ddi_depth_stencilop_desc.md) structure that describes the stencil operation to perform on forward-facing polygons.

### -field BackFace
 
A [D3D12DDI_DEPTH_STENCILOP_DESC](ns-d3d12umddi-d3d12ddi_depth_stencilop_desc.md) structure that describes the stencil operation to perform on back-facing polygons.

## -remarks

If the StencilEnable member is set to TRUE, the FrontEnable member, BackEnable member, or both must also be set to TRUE.

## -see-also
