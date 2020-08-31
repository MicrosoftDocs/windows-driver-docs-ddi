---
UID: NC:d3d12umddi.PFND3D12DDI_BEGIN_RENDER_PASS_0053
title: PFND3D12DDI_BEGIN_RENDER_PASS_0053 (d3d12umddi.h)
description: Implemented by the client driver to start the Render Pass.
ms.assetid: 8d08ba4b-1869-45e6-aed2-267bb3db4bf5
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_BEGIN_RENDER_PASS_0053 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
 - PFND3D12DDI_BEGIN_RENDER_PASS_0053
 - d3d12umddi/PFND3D12DDI_BEGIN_RENDER_PASS_0053
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_BEGIN_RENDER_PASS_0053
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_BEGIN_RENDER_PASS_0053 callback function


## -description

Implemented by the client driver to start the Render Pass.

## -parameters

### -param Arg1

List of commands.

### -param NumRenderTargets

The number of rendering targets.

### -param pRenderTargets

*_In_reads_opt_(NumRenderTargets)*

Pointer to the [D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053](ns-d3d12umddi-d3d12ddiarg_render_pass_render_target_desc_0053.md) structure, that specifies the render target.

### -param pDepthStencil

*_In_opt_*

Pointer to [D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC_0053](ns-d3d12umddi-d3d12ddiarg_render_pass_depth_stencil_desc_0053.md), that provides information about the Render Pass depth stencil.

### -param Flags

Pointer to a [D3D12DDIARG_RENDER_PASS_FLAGS_0053](ne-d3d12umddi-d3d12ddiarg_render_pass_flags_0053.md) enumeration, that specifies the state of the Render Pass.

## -prototype

```cpp
//Declaration

PFND3D12DDI_BEGIN_RENDER_PASS_0053 Pfnd3d12ddiBeginRenderPass0053; 

// Definition

VOID Pfnd3d12ddiBeginRenderPass0053 
(
	D3D12DDI_HCOMMANDLIST Arg1
	UINT NumRenderTargets
	CONST D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC_0053 *pRenderTargets
	CONST D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC_0053 *pDepthStencil
	D3D12DDIARG_RENDER_PASS_FLAGS_0053 Flags
)
{...}

```

## -remarks

When calling Pfnd3d12ddiBeginRenderPass, the user must declare all Resources that can be one or both of the following:

* Serving as RTVs (Render Target View) or DSVs (Data Source View) within that Render Pass, and/or
* ‘resuming’ from a previous Render Pass, via a SUSPEND/RESUME pair.

The [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type_0053.md) and [D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md) enumerations must both be provided for all resources when calling this callback.

## -see-also

