---
UID: NE:d3d12umddi.D3D12DDI_RENDER_PASS_TIER
title: D3D12DDI_RENDER_PASS_TIER (d3d12umddi.h)
description: The extent to which a UMD efficiently supports Render Pass.
ms.date: 09/22/2022
keywords: ["D3D12DDI_RENDER_PASS_TIER enumeration"]
ms.keywords: D3D12DDI_RENDER_PASS_TIER, D3D12DDI_RENDER_PASS_TIER,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RENDER_PASS_TIER
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RENDER_PASS_TIER
 - d3d12umddi/D3D12DDI_RENDER_PASS_TIER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RENDER_PASS_TIER
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_RENDER_PASS_TIER enumeration

## -description

A **D3D12DDI_RENDER_PASS_TIER** value indicates the level of support that a user-mode driver (UMD) provides for render passes.

## -enum-fields

### -field D3D12DDI_RENDER_PASS_TIER_NOT_SUPPORTED:0

The UMD has not implemented a DDI Table, which is supported via software emulation.

### -field D3D12DDI_RENDER_PASS_TIER_1:1

The driver provides tier 1 support.

### -field D3D12DDI_RENDER_PASS_TIER_2:2

The driver provides tier 2 support.

## -remarks

See [**D3D12_VIEW_INSTANCING_TIER**](/windows/win32/api/d3d12/ne-d3d12-d3d12_tiled_resources_tier) for a detailed description for each tier level.

The UMD will report back these tiers to the runtime. The runtime will validate that UMDs that fill out the DDI table report back at least TIER_1 support. At the same time, the runtime will validate that UMDs that do not fill out the DDI table do not claim anything other than TIER_0 support (the runtime will fail device creation in this case).

> [!NOTE]
> This requirement will only be present for UMDs that support the DDI build version in which this change is made.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0089**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0089.md)
