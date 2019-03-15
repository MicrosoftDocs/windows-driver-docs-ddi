---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_FUNCS_0053
title: D3D12DDI_RENDER_PASS_FUNCS_0053 (d3d12umddi.h)
description: Callback functions used to begin and end a Render Pass.
ms.assetid: ab8673e4-9631-43bb-ab56-79b2c65019ee
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_RENDER_PASS_FUNCS_0053, D3D12DDI_RENDER_PASS_FUNCS_0053, 
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
req.typenames: D3D12DDI_RENDER_PASS_FUNCS_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RENDER_PASS_FUNCS_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RENDER_PASS_FUNCS_0053 structure

## -description

Callback functions used to begin and end a Render Pass.

## -struct-fields

### -field pfnBeginRenderPass

Pointer to the [PFND3D12DDI_BEGIN_RENDER_PASS_0053](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md) callback to begin a Render Pass.

### -field pfnEndRenderPass
 
Pointer to the [PFND3D12DDI_END_RENDER_PASS_0053](nc-d3d12umddi-pfnd3d12ddi_end_render_pass_0053.md) callback to end a Render Pass.

## -remarks

## -see-also
