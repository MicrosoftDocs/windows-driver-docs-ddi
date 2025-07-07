---
UID: NC:d3d12umddi.PFND3D12DDI_END_RENDER_PASS
title: PFND3D12DDI_END_RENDER_PASS (d3d12umddi.h)
description: Learn more about the PFND3D12DDI_END_RENDER_PASS callback function.
ms.date: 03/28/2025
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_END_RENDER_PASS
 - d3d12umddi/PFND3D12DDI_END_RENDER_PASS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_END_RENDER_PASS
dev_langs:
 - c++
---

# PFND3D12DDI_END_RENDER_PASS callback function

## -description

The user-mode display driver's (UMD) **pfnEndRenderPass** callback function marks the end of a render pass.

## -parameters

### -param unnamedParam1

[in] A D3D12DDI_HCOMMANDLIST (command list) that contains the Render Pass.

## -remarks

For the [extended render passes feature](/windows-hardware/drivers/display/d3d12-render-passes), the [**PFND3D12DDI_END_RENDER_PASS_0053**](nc-d3d12umddi-pfnd3d12ddi_end_render_pass_0053.md) function is called instead.

## -see-also

[**pfnBeginRenderPass**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass.md)
