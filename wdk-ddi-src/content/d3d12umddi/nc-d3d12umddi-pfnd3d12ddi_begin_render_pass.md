---
UID: NC:d3d12umddi.PFND3D12DDI_BEGIN_RENDER_PASS
title: PFND3D12DDI_BEGIN_RENDER_PASS (d3d12umddi.h)
description: Learn more about the PFND3D12DDI_BEGIN_RENDER_PASS callback function.
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
 - PFND3D12DDI_BEGIN_RENDER_PASS
 - d3d12umddi/PFND3D12DDI_BEGIN_RENDER_PASS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_BEGIN_RENDER_PASS
dev_langs:
 - c++
---

# PFND3D12DDI_BEGIN_RENDER_PASS callback function

## -description

This version of the user-mode display driver's (UMD) **pfnBeginRenderPass** callback function marks the start of a render pass.

## -parameters

### -param unnamedParam1

[in] A D3D12DDI_HCOMMANDLIST handle through which to reference the command list.

### -param NumRenderTargets

[in/optional] The number of rendering targets that **pRenderTargets** points to.

### -param pRenderTargets

[in/optional] Pointer to a [**D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC**](ns-d3d12umddi-d3d12ddiarg_render_pass_render_target_desc.md) structure that describes the render target.

### -param pDepthStencil

[in/optional] Pointer to a [**D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC**](ns-d3d12umddi-d3d12ddiarg_render_pass_depth_stencil_desc.md) structure that describes the render pass depth stencil.

### -param UnorderedAccessViewAccessFlags

[in] An unordered access view (UAV), defined by a value in the [**D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS**](ne-d3d12umddi-d3d12ddiarg_render_pass_uav_access_flags.md) enumeration.

## -remarks

For the [extended render passes feature](/windows-hardware/drivers/display/d3d12-render-passes), the [**PFND3D12DDI_BEGIN_RENDER_PASS_0053**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md) function is called instead.

The caller of **pfnBeginRenderPass** must provide all Resources that the user declared. These resources can be one or both of the following:

* Serving as RTVs (Render Target View) or DSVs (Data Source View) within that Render Pass.
* Resuming from a previous Render Pass, via a SUSPEND/RESUME pair.

The [**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE**](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type.md) and [**D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE**](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type.md) enumerations must both be provided for all resources when calling this callback.

## -see-also

[**pfnEndRenderPass**](nc-d3d12umddi-pfnd3d12ddi_end_render_pass.md)
