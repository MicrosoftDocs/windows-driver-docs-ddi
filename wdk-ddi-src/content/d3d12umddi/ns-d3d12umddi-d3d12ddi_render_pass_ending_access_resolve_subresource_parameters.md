---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS
title: D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS
author: windows-driver-content
description: Used in the D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS structure, to specify the subresource to resolve while the Render Pass is ending access.
ms.assetid: 51a3612b-3600-4a55-ae3c-b03bb1960790
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS, D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS, 
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
req.typenames: D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_SUBRESOURCE_PARAMETERS structure

## -description

Used in the [D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_resolve_parameters.md) structure, to specify the subresource to resolve while the Render Pass is ending access.

## -struct-fields

### -field SrcSubresource

A handle to the command list structure that the resolve subresource will be transitioned to at the time the Render Pass ends.

### -field DstSubresource

A handle to the command list that the resolve subresource destination will be at the time the Render Pass ends.

### -field DstX

The X coordinate of the left-most edge of the destination region. The width of the destination region is the same as the width of the source rectangle.

### -field DstY

The Y coordinate of the top-most edge of the destination region. The height of the destination region is the same as the height of the source rectangle.

### -field SrcRect

Specifies the rectangular region of the source subresource to be resolved. 

## -remarks

## -see-also