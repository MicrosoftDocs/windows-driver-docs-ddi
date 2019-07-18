---
UID: NC:d3d12umddi.PFND3D12DDI_BEGIN_RENDER_PASS
title: PFND3D12DDI_BEGIN_RENDER_PASS (d3d12umddi.h)
description: Implemented by the client driver to start the Render Pass. 
ms.assetid: 563ef6fb-d509-4f6b-8a2f-95cfcaea8dd7
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_BEGIN_RENDER_PASS"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_BEGIN_RENDER_PASS
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_BEGIN_RENDER_PASS callback function

## -description

Implemented by the client driver to start the Render Pass. 

## -prototype

```cpp
//Declaration

PFND3D12DDI_BEGIN_RENDER_PASS Pfnd3d12ddiBeginRenderPass; 

// Definition

VOID Pfnd3d12ddiBeginRenderPass 
(
	D3D12DDI_HCOMMANDLIST Arg1
	UINT NumRenderTargets
	CONST D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC *pRenderTargets
	CONST D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC *pDepthStencil
	D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS UnorderedAccessViewAccessFlags
)
{...}

```

## -parameters

### -param Arg1

List of commands.

### -param NumRenderTargets

The number of rendering targets.

### -param *pRenderTargets

*_In_reads_opt_(NumRenderTargets)*


Pointer to the [D3D12DDIARG_RENDER_PASS_RENDER_TARGET_DESC](ns-d3d12umddi-d3d12ddiarg_render_pass_render_target_desc.md) structure, that specifies the render target.

### -param *pDepthStencil

*_In_opt_*

Pointer to [D3D12DDIARG_RENDER_PASS_DEPTH_STENCIL_DESC](ns-d3d12umddi-d3d12ddiarg_render_pass_depth_stencil_desc.md), that provides information about the render pass depth stencil.

### -param UnorderedAccessViewAccessFlags


An unordered access view (UAV), defined by a value in the [D3D12DDIARG_RENDER_PASS_UAV_ACCESS_FLAGS](ne-d3d12umddi-d3d12ddiarg_render_pass_uav_access_flags.md) enumeration.


## -returns

Returns VOID.

## -remarks

When calling Pfnd3d12ddiBeginRenderPass, the user must declare all Resources that can be one or both of the following:

* Serving as RTVs (Render Target View) or DSVs (Data Source View) within that Render Pass, and/or
* ‘resuming’ from a previous Render Pass, via a SUSPEND/RESUME pair.

The [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type.md) and [D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type.md) enumerations must both be provided for all resources when calling this callback.

## -see-also
