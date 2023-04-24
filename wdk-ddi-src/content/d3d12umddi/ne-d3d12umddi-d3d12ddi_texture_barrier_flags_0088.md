---
UID: NE:d3d12umddi.D3D12DDI_TEXTURE_BARRIER_FLAGS_0088
tech.root: display
title: D3D12DDI_TEXTURE_BARRIER_FLAGS_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_TEXTURE_BARRIER_FLAGS_0088 enumeration.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_TEXTURE_BARRIER_FLAGS_0088
f1_keywords:
 - D3D12DDI_TEXTURE_BARRIER_FLAGS_0088
 - d3d12umddi/D3D12DDI_TEXTURE_BARRIER_FLAGS_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_TEXTURE_BARRIER_FLAGS_0088
---

## -description

The **D3D12DDI_TEXTURE_BARRIER_FLAGS_0088** enumeration specifies flags for texture resource barriers.

## -enum-fields

### -field D3D12DDI_TEXTURE_BARRIER_FLAG_NONE:0x0

No flags are specified.

### -field D3D12DDI_TEXTURE_BARRIER_FLAG_DISCARD:0x1

This flag can only be used when [**LayoutBefore**](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md) is **D3D12_BARRIER_LAYOUT_UNDEFINED**. Typically, this flag is used to initialize compression metadata as part of a barrier that activates an aliased resource. The [**Subresource**](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md) member must indicate all subresources. Without this flag, a full resource Clear, Copy or Discard is required before use.

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDI_TEXTURE_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md)
