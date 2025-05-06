---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053
title: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053 (d3d12umddi.h)
description: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053 contains parameters that specify whether the application has a dependency on the resource being cleared.
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
req.typenames: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053
 - d3d12umddi/D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053
dev_langs:
 - c++
---

# D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053 structure

## -description

The **D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053** structure describes the clear value to which resource(s) should be cleared at the beginning of a render pass.

## -struct-fields

### -field ClearValue

A [**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md) structure that specifies the clear parameters to which the resource(s) should be cleared.

## -remarks

This structure is used when the beginning access [**Type**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_0053.md) for a resource within a render pass is **D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053_CLEAR**.

For more information, see [D3D12 Render Passes](/windows-hardware/drivers/display/d3d12-render-passes).

## -see-also

[**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_0053.md)

[**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053**](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type_0053.md)

[**D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053**](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md)
[**pfnBeginRenderPass**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md)