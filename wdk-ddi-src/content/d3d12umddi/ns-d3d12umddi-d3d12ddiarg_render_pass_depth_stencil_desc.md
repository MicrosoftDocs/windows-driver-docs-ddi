---
UID: NS:d3d12umddi.D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC
title: D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC (d3d12umddi.h)
description: 
ms.assetid: 87983276-c1f7-4ffe-8cd3-c1bb8ffee250
ms.date: 10/19/2018
keywords: ["D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC"
 - "D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC"
ms.keywords: D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC, D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC, 
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
req.typenames: D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC structure

## -description

Describes the Render Pass depth-stencil state.

## -struct-fields

### -field cpuDescriptor

The [D3D12DDI_CPU_DESCRIPTOR_HANDLE](ns-d3d12umddi-d3d12ddi_cpu_descriptor_handle.md) structure that defines the depth buffer bindings.

### -field DepthBeginningAccess

A [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_0053.md) structure that specifies the access mode for the depth, when a Render Pass is beginning.

### -field StencilBeginningAccess

A [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_0053.md) structure that specifies the access mode for the stencil, when a Render Pass is beginning.

### -field DepthEndingAccess

A [D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_0053.md) structure that specifies the access mode for the depth, when a Render Pass is ending.

### -field StencilEndingAccess

A [D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_0053.md) structure that specifies the access mode for the stencil, when a Render Pass is ending.

## -remarks

## -see-also
