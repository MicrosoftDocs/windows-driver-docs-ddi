---
UID: NE:d3d12umddi.D3D12DDI_HEAP_FLAGS
title: D3D12DDI_HEAP_FLAGS (d3d12umddi.h)
description: Contains Direct3D 12 heap flags.
old-location: display\d3d12ddi_heap_flags.htm
ms.date: 09/22/2022
keywords: ["D3D12DDI_HEAP_FLAGS enumeration"]
ms.keywords: D3D12DDI_HEAP_FLAGS, D3D12DDI_HEAP_FLAGS enumeration [Display Devices], D3D12DDI_HEAP_FLAG_BUFFERS, D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE, D3D12DDI_HEAP_FLAG_CONTENT_PROTECTION, D3D12DDI_HEAP_FLAG_NONE, D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES, D3D12DDI_HEAP_FLAG_PRIMARY, D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES, d3d12umddi/D3D12DDI_HEAP_FLAGS, d3d12umddi/D3D12DDI_HEAP_FLAG_BUFFERS, d3d12umddi/D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE, d3d12umddi/D3D12DDI_HEAP_FLAG_CONTENT_PROTECTION, d3d12umddi/D3D12DDI_HEAP_FLAG_NONE, d3d12umddi/D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES, d3d12umddi/D3D12DDI_HEAP_FLAG_PRIMARY, d3d12umddi/D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES, display.d3d12ddi_heap_flags
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_HEAP_FLAGS
f1_keywords:
 - D3D12DDI_HEAP_FLAGS
 - d3d12umddi/D3D12DDI_HEAP_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_HEAP_FLAGS
---

# D3D12DDI_HEAP_FLAGS enumeration

## -description

The **D3D12DDI_HEAP_FLAGS** enumeration specifies Direct3D 12 heap options.

## -enum-fields

### -field D3D12DDI_HEAP_FLAG_NONE:0x0

No flags.

### -field D3D12DDI_HEAP_FLAG_NON_RT_DS_TEXTURES:0x2

The heap supports resources allocated for other than Render Target (RT) and Depth-Stencil (DS) textures.

### -field D3D12DDI_HEAP_FLAG_BUFFERS:0x4

The heap supports resources allocated for buffers.

### -field D3D12DDI_HEAP_FLAG_COHERENT_SYSTEMWIDE:0x8

The heap supports resources allocated for coherent system wide.

### -field D3D12DDI_HEAP_FLAG_PRIMARY:0x10

The heap supports resources allocated for primary.

### -field D3D12DDI_HEAP_FLAG_RT_DS_TEXTURES:0x20

The heap supports resources allocated for RT and DS textures.

### -field D3D12DDI_HEAP_FLAG_0041_DENY_L0_DEMOTION:0x40

Supports transparent demotion to system memory by restricting the supported memory segments for the heap.

## -see-also

[**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md)
