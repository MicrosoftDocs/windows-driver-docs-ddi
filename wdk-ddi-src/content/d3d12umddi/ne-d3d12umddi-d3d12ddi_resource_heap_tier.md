---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_HEAP_TIER
title: D3D12DDI_RESOURCE_HEAP_TIER (d3d12umddi.h)
description: Specifies which resource heap tier the hardware and driver support.
ms.date: 09/22/2022
keywords: ["D3D12DDI_RESOURCE_HEAP_TIER enumeration"]
ms.keywords: D3D12DDI_RESOURCE_HEAP_TIER, D3D12DDI_RESOURCE_HEAP_TIER,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RESOURCE_HEAP_TIER
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - D3D12DDI_RESOURCE_HEAP_TIER
 - d3d12umddi/D3D12DDI_RESOURCE_HEAP_TIER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RESOURCE_HEAP_TIER
dev_langs:
 - c++
---

# D3D12DDI_RESOURCE_HEAP_TIER enumeration

## -description

A **D3D12DDI_RESOURCE_HEAP_TIER** value specifies which resource heap tier the hardware and driver support.

## -enum-fields

### -field D3D12DDI_RESOURCE_HEAP_TIER_1:1

Indicates that heaps can only support resources from a single resource category.

### -field D3D12DDI_RESOURCE_HEAP_TIER_2:2

Indicates that heaps can support resources from all three categories.

## -remarks

See [**D3D12_RESOURCE_HEAP_TIER **](/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_heap_tier) for a detailed description for each tier level.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0089**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0089.md)
