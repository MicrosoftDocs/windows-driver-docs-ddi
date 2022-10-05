---
UID: NE:d3d12umddi.D3D12DDI_TILED_RESOURCES_TIER
tech.root: display
title: D3D12DDI_TILED_RESOURCES_TIER
ms.date: 09/22/2022
targetos: Windows
description: Learn more about the D3D12DDI_TILED_RESOURCES_TIER enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
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
 - D3D12DDI_TILED_RESOURCES_TIER
f1_keywords:
 - D3D12DDI_TILED_RESOURCES_TIER
 - d3d12umddi/D3D12DDI_TILED_RESOURCES_TIER
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_TILED_RESOURCES_TIER
---

## -description

A **D3D12DDI_TILED_RESOURCES_TIER** value identifies the tier level at which the driver supports tiled resources.

## -enum-fields

### -field D3D12DDI_TILED_RESOURCES_TIER_NOT_SUPPORTED:0

The driver does not support tiled resources.

### -field D3D12DDI_TILED_RESOURCES_TIER_1:1

The driver provides tier 1 support for tiled resources.

### -field D3D12DDI_TILED_RESOURCES_TIER_2:2

The driver provides tier 2 support for tiled resources.

### -field D3D12DDI_TILED_RESOURCES_TIER_3:3

The driver provides tier 3 support for tiled resources.

## -remarks

See [**D3D12_TILED_RESOURCES_TIER**](/windows/win32/api/d3d12/ne-d3d12-d3d12_tiled_resources_tier) for a detailed description for each tier level.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0089**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0089.md)
