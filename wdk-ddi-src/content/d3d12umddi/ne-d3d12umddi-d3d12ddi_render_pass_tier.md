---
UID: NE:d3d12umddi.D3D12DDI_RENDER_PASS_TIER
title: D3D12DDI_RENDER_PASS_TIER (d3d12umddi.h)
description: The extent to which a UMD efficiently supports Render Pass.
ms.assetid: 7cd2f2a1-af74-44e6-b094-06e6c02443c7
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "d3d12umddi/D3D12DDI_RENDER_PASS_TIER"
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
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RENDER_PASS_TIER enumeration

## -description

The extent to which a UMD (user mode driver) efficiently supports Render Pass.

## -enum-fields

### -field D3D12DDI_RENDER_PASS_TIER_NOT_SUPPORTED

The UMD has not implemented a DDI Table, which is supported via software emulation.

### -field D3D12DDI_RENDER_PASS_TIER_1

Render Passes implemented by UMD, RT/DB writes may be accelerated. UAV (user access view) writes are not efficiently supported within the Render Pass.

### -field D3D12DDI_RENDER_PASS_TIER_2 

Includes Tier 1, plus UAV writes, pursuant to the read-after-write prohibition, are likely to be efficiently supported. This is more efficient than issuing the same work without a Render Pass.

## -remarks

The UMD will report back these tiers to the runtime. The runtime will validate that UMDs which fill out the DDI table at least report back TIER_1, and at the same time will validate that UMDs which do not fill out the DDI table do not claim anything other than TIER_0 support (the runtime will fail device creation in this case).

> [!NOTE]
> This requirement will only be present for UMDs that support a the DDI build version in which this change is made.

## -see-also
