---
UID: NE:d3d12umddi.D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE
title: D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE (d3d12umddi.h)
description: Indicates that the application will have no future dependencies on the data written to the resource during this Render Pass.
ms.assetid: 19119cc2-5c96-48ca-81fc-634eaf99bf36
ms.date: 10/19/2018
ms.keywords: D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE, D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE enumeration

## -description

## -enum-fields

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_DISCARD

Indicates that the application will have no future dependencies on the data written to the resource during this Render Pass. However, dependencies may be appropriate for a depth buffer where the depth buffer will never be textured from prior to future writes.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE

Indicates that the application will have a dependency on the written contents of this resource in the future, and they must be preserved.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE

Allows the application to directly resolve a MSAA (Multisampling anti-aliasing) surface to a separate resource at the conclusion of the Render Pass. Ideally, this is done while the MSAA contents are currently in the tile cache, for TBDRs (Tile Based Deferred Rendering).
The resolve destination is expected to be in the *hDstResource* resource state field of the [D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_resolve_parameters.md) structure, at the time the Render Pass ends.
The resolve source will be transitioned to the *hSrcResource* resource state of the [[D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_resolve_parameters.md) structure, at the time the Render Pass ends.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_NO_ACCESS

Indicates the resource will not be read from or written to during the Render Pass. It is most expected to used to denote whether the depth/stencil plane for a DSV is not accessed.

> [!IMPORTANT] 
> This value must be paired with the *D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_NO_ACCESS* value of the [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type.md) enumeration.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_SUSPEND_WRITING

Indicates that the application will continue writing to the resource in an immediately succeeding Render Pass, with no intervening GPU work.

### -field D3D12DDI_RENDER_PASS_ENDING_ACCESS_SUSPEND_LOCAL_READ

Indicates that the application has written to the resource, and it will read from the resource in the future in a one-to-one (plus optional gutter pixels) fashion. In the pixel shader, only the current pixel plus an optional number of surrounding pixels will be read from. This enumeration also indicates that no GPU operations will occur between SUSPEND and RESUME.

## -remarks

## -see-also

