---
UID: NS:d3d12umddi.D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
title: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053 (d3d12umddi.h)
description: The D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053 structure describes the render target. This structure is declared at the start of a render pass.
ms.date: 03/28/2025
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
req.typenames: D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
 - d3d12umddi/D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053
dev_langs:
 - c++
---

# D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053 structure

## -description

The **D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053** structure describes the bindings to one or more render target views (RTVs), as well as their beginning and ending access characteristics.

## -struct-fields

### -field cpuDescriptor

The [**D3D12DDI_CPU_DESCRIPTOR_HANDLE**](ns-d3d12umddi-d3d12ddi_cpu_descriptor_handle.md) structure that is the CPU descriptor handle corresponding to the render target view(s) (RTVs).

### -field BeginningAccess

A [**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_0053.md) structure that identifies the requested access to the RTV(s) at the transition into a render pass.

### -field EndingAccess

A [**D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053**](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_0053.md) structure that identifies the requested access to the RTV(s) at the transition out of a render pass.

## -remarks

This structure is declared at the start of a Render Pass.

For more information, see [D3D12 Render Passes](/windows-hardware/drivers/display/render-passes).

## -see-also

[**pfnBeginRenderPass**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md)
