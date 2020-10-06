---
UID: NS:d3d12umddi.D3D12DDI_DEPTH_STENCILOP_DESC
title: D3D12DDI_DEPTH_STENCILOP_DESC (d3d12umddi.h)
description: Describes stencil operations that can be performed based on the results of stencil test.
ms.assetid: e906c6d4-e4eb-42ad-b983-0fe3e4b8c498
ms.date: 10/19/2018
keywords: ["D3D12DDI_DEPTH_STENCILOP_DESC structure"]
ms.keywords: D3D12DDI_DEPTH_STENCILOP_DESC, D3D12DDI_DEPTH_STENCILOP_DESC,
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
req.typenames: D3D12DDI_DEPTH_STENCILOP_DESC
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_DEPTH_STENCILOP_DESC
 - d3d12umddi/D3D12DDI_DEPTH_STENCILOP_DESC
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DEPTH_STENCILOP_DESC
dev_langs:
 - c++
---

# D3D12DDI_DEPTH_STENCILOP_DESC structure


## -description

The D3D12DDI_DEPTH_STENCILOP_DESC structure describes stencil operations that can be performed based on the results of stencil test.

## -struct-fields

### -field StencilFailOp

A [D3D12DDI_STENCIL_OP](ne-d3d12umddi-d3d12ddi_stencil_op.md)-typed value that indicates the operation to perform if the stencil test fails.

### -field StencilDepthFailOp

A [D3D12DDI_STENCIL_OP](ne-d3d12umddi-d3d12ddi_stencil_op.md)-typed value that indicates the operation to perform if the stencil test passes and the depth test fails.

### -field StencilPassOp

A [D3D12DDI_STENCIL_OP](ne-d3d12umddi-d3d12ddi_stencil_op.md)-typed value that indicates the operation to perform if both stencil and depth tests pass.

### -field StencilFunc

 
A [D3D12DDI_COMPARISON_FUNC](ne-d3d12umddi-d3d12ddi_comparison_func.md)-typed value that indicates the stencil-comparison function to perform.

## -remarks

## -see-also

