---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS
title: D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS (d3d12umddi.h)
description: Holds the parameters used in the D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053 structure, when the Render Pass is ending access.
ms.assetid: b8f4b925-15e6-48d4-8186-0005219796d8
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS"
ms.keywords: D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS, D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS, 
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
req.typenames: D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS structure

## -description

Holds the parameters used in the [D3D12DDI_RENDER_PASS_ENDING_ACCESS](ns-d3d12umddi-d3d12ddi_render_pass_ending_access.md) structure, when the Render Pass is ending access.

## -struct-fields

### -field hSrcResource

A handle to the command list structure that the resolve source will be transitioned to at the time the Render Pass ends.

### -field hDstResource

A handle to the command list that the resolve destination will be at the time the Render Pass ends.

### -field SubresourceCount

The count of subresources that are a part of the command list.

### -field pSubresourceParameters

A pointer to a [D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_resolve_subresource_parameters.md) structure that represents the subresource parameters to resolve while the Render Pass is ending.

### -field Format

The format, represented in DXGI_FORMAT.

### -field ResolveMode

The [resolve mode](ne-d3d12umddi-d3d12ddi_resolve_mode.md) to use while the Render Pass is ending.

## -remarks

## -see-also
