---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_TIER
title: D3D12DDI_RAYTRACING_TIER (d3d12umddi.h)
description: Specifies the ray tracing tier.
ms.date: 09/22/2022
keywords: ["D3D12DDI_RAYTRACING_TIER enumeration"]
ms.keywords: D3D12DDI_RAYTRACING_TIER, D3D12DDI_RAYTRACING_TIER,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RAYTRACING_TIER
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RAYTRACING_TIER
 - d3d12umddi/D3D12DDI_RAYTRACING_TIER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RAYTRACING_TIER
dev_langs:
 - c++
---

# D3D12DDI_RAYTRACING_TIER enumeration

## -description

A **D3D12DDI_RAYTRACING_TIER** value specifies the level of raytracing support provided by the graphics hardware.

## -enum-fields

### -field D3D12DDI_RAYTRACING_TIER_NOT_SUPPORTED:0

There is no support for raytracing on the device.

### -field D3D12DDI_RAYTRACING_TIER_1_0:10

The device supports tier 1 raytracing.

### -field D3D12DDI_RAYTRACING_TIER_1_1:11

The device supports tier 1.1 raytracing. Available starting with Windows 10, version 2004.

## -remarks

See [**D3D12_RAYTRACING_TIER**](/windows/win32/api/d3d12/ne-d3d12-d3d12_raytracing_tier) for a detailed description for each tier level.

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_0089**](ns-d3d12umddi-d3d12ddi_d3d12_options_data_0089.md)
