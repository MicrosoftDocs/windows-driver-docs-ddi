---
UID: NE:d3d12umddi.D3D12DDI_VIEW_INSTANCING_TIER
title: D3D12DDI_VIEW_INSTANCING_TIER (d3d12umddi.h)
description: Defines the view instancing tier.
old-location: display\d3d12ddi-view-instancing-tier.htm
ms.date: 09/22/2022
keywords: ["D3D12DDI_VIEW_INSTANCING_TIER enumeration"]
ms.keywords: D3D12DDI_VIEW_INSTANCING_TIER, D3D12DDI_VIEW_INSTANCING_TIER enumeration [Display Devices], D3D12DDI_VIEW_INSTANCING_TIER_1, D3D12DDI_VIEW_INSTANCING_TIER_2, D3D12DDI_VIEW_INSTANCING_TIER_3, D3D12DDI_VIEW_INSTANCING_TIER_NOT_SUPPORTED, d3d12umddi/D3D12DDI_VIEW_INSTANCING_TIER, d3d12umddi/D3D12DDI_VIEW_INSTANCING_TIER_1, d3d12umddi/D3D12DDI_VIEW_INSTANCING_TIER_2, d3d12umddi/D3D12DDI_VIEW_INSTANCING_TIER_3, d3d12umddi/D3D12DDI_VIEW_INSTANCING_TIER_NOT_SUPPORTED, display.d3d12ddi-view-instancing-tier
req.header: d3d12umddi.h
req.include-header: 
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
req.typenames: D3D12DDI_VIEW_INSTANCING_TIER
f1_keywords:
 - D3D12DDI_VIEW_INSTANCING_TIER
 - d3d12umddi/D3D12DDI_VIEW_INSTANCING_TIER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIEW_INSTANCING_TIER
---

# D3D12DDI_VIEW_INSTANCING_TIER enumeration

## -description

A **D3D12DDI_VIEW_INSTANCING_TIER** value indicates the tier level at which the driver supports view instancing.

## -enum-fields

### -field D3D12DDI_VIEW_INSTANCING_TIER_NOT_SUPPORTED

View instancing is not supported.

### -field D3D12DDI_VIEW_INSTANCING_TIER_1

The driver provides tier 1 support.

### -field D3D12DDI_VIEW_INSTANCING_TIER_2

The driver provides tier 2 support.

### -field D3D12DDI_VIEW_INSTANCING_TIER_3

The driver provides tier 1 support.

## -remarks

See [**D3D12_VIEW_INSTANCING_TIER**](/windows/win32/api/d3d12/ne-d3d12-d3d12_tiled_resources_tier) for a detailed description for each tier level.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0089**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0089.md)