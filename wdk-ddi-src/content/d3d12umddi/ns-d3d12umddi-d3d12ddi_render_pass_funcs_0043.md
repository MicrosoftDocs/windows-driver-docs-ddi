---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_FUNCS_0043
title: D3D12DDI_RENDER_PASS_FUNCS_0043 (d3d12umddi.h)
description: The D3D12DDI_RENDER_PASS_FUNCS_0043 structure contains callback functions used to begin and end a render pass.
ms.date: 10/19/2018
keywords: ["D3D12DDI_RENDER_PASS_FUNCS_0043 structure"]
ms.keywords: D3D12DDI_RENDER_PASS_FUNCS_0043, D3D12DDI_RENDER_PASS_FUNCS_0043,
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
req.typenames: D3D12DDI_RENDER_PASS_FUNCS_0043
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RENDER_PASS_FUNCS_0043
 - d3d12umddi/D3D12DDI_RENDER_PASS_FUNCS_0043
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RENDER_PASS_FUNCS_0043
dev_langs:
 - c++
---

# D3D12DDI_RENDER_PASS_FUNCS_0043 structure


## -description

Callback functions used to begin and end a Render Pass.

## -struct-fields

### -field pfnBeginRenderPass

Pointer to the [PFND3D12DDI_BEGIN_RENDER_PASS](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass.md) callback to begin a Render Pass.

### -field pfnEndRenderPass

 
Pointer to the [PFND3D12DDI_END_RENDER_PASS](nc-d3d12umddi-pfnd3d12ddi_end_render_pass.md) callback to end a Render Pass.

## -remarks

## -see-also

