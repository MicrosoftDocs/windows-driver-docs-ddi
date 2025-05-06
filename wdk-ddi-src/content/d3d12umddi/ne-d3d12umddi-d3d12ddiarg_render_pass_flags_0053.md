---
UID: NE:d3d12umddi.D3D12DDIARG_RENDER_PASS_FLAGS_0053
title: D3D12DDIARG_RENDER_PASS_FLAGS_0053 (d3d12umddi.h)
description: Learn more about the D3D12DDIARG_RENDER_PASS_FLAGS_0053 enumeration.
ms.date: 03/28/2025
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDIARG_RENDER_PASS_FLAGS_0053
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDIARG_RENDER_PASS_FLAGS_0053
 - d3d12umddi/D3D12DDIARG_RENDER_PASS_FLAGS_0053
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_RENDER_PASS_FLAGS_0053
dev_langs:
 - c++
---

# D3D12DDIARG_RENDER_PASS_FLAGS_0053 enumeration

## -description

The **D3D12DDIARG_RENDER_PASS_FLAGS_0053** enumeration is a bitwise OR of flags that indicate the state of a render pass.

## -enum-fields

### -field D3D12DDI_RENDER_PASS_FLAG_0053_NONE:0x0

No flags are specified.

### -field D3D12DDI_RENDER_PASS_FLAG_0053_ALLOW_UAV_WRITES:0x1

Used to specify whether the user will be issuing UAV writes within the render pass, allowing UMDs (user mode drivers) to opt out of tiling if necessary.

### -field D3D12DDI_RENDER_PASS_FLAG_0053_SUSPENDING_PASS:0x2

This render pass is suspending.

### -field D3D12DDI_RENDER_PASS_FLAG_0053_RESUMING_PASS:0x4

This render pass is resuming.

### -field D3D12DDI_RENDER_PASS_FLAG_0101_BIND_READ_ONLY_DEPTH:0x8

A depth stencil view (DSV) should be bound as read-only for the depth aspect during the render pass. This flag is set when the depth data will be read by the GPU, such as for depth comparison in shadow mapping, but not written to during the pass. This flag can only be specified for a depth surface that was initialized before the current pass (by a previous pass or some other way).

### -field D3D12DDI_RENDER_PASS_FLAG_0101_BIND_READ_ONLY_STENCIL:0x10

The stencil aspect of a DSV should be bound as read-only during the render pass. This is useful when the stencil data is needed for read operations like stencil testing but will not be modified by the pass. This flag can only be specified for a stencil surface that was initialized before the current pass (by a previous pass or some other way).

## -remarks

A render pass can be both resuming and suspending.

For more information, see [D3D12 Render Passes](/windows-hardware/drivers/display/d3d12-render-passes).

## -see-also

[**pfnBeginRenderPass**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md)
