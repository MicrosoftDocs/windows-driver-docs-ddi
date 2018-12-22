---
UID: NE:d3d12umddi.D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053
title: D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053
description: 
ms.assetid: 8816fc0d-1f78-4310-a036-e4278a4a6c71
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053, D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053 enumeration

## -description



## -enum-fields

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053_DISCARD

Indicates that the application will have no future dependencies on the data written to the resource during this Render Pass. However, dependencies may be appropriate for a depth buffer where the depth buffer will never be textured from prior to future writes.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053_PRESERVE

Indicates that the application will have a dependency on the written contents of this resource in the future, and they must be preserved.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053_RESOLVE

Allows the application to directly resolve a MSAA (Multisampling anti-aliasing) surface to a separate resource at the conclusion of the Render Pass. Ideally, this is done while the MSAA contents are currently in the tile cache, for TBDRs (Tile Based Deferred Rendering).
The resolve destination is expected to be in the *hDstResource* resource state field of the [D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS_0053](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_resolve_parameters_0053.md) structure, at the time the Render Pass ends.
The resolve source will be transitioned to the *hSrcResource* resource state of the [D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS_0053](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_resolve_parameters_0053.md) structure, at the time the Render Pass ends.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053_NO_ACCESS 

signifies the resource will not be read from or written to during the Render Pass. It is most expected to used to denote whether the depth/stencil plane for a DSV is not accessed.

> [!IMPORTANT] 
> This value must be paired with the *D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_NO_ACCESS* value of the [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type_0053.md) enumeration.

## -remarks

## -see-also
