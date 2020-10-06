---
UID: NE:d3d12umddi.D3D12DDI_VARIABLE_SHADING_RATE_TIER
title: D3D12DDI_VARIABLE_SHADING_RATE_TIER
description: Indicates the tier at which variable rate shading occurs.
tech.root: display
ms.assetid: 52c5d637-560d-4bf7-99f9-484adbbadfd3
ms.date: 04/04/2019
keywords: ["D3D12DDI_VARIABLE_SHADING_RATE_TIER enumeration"]
ms.keywords: D3D12DDI_VARIABLE_SHADING_RATE_TIER, D3D12DDI_VARIABLE_SHADING_RATE_TIER,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_VARIABLE_SHADING_RATE_TIER
targetos: Windows
ms.custom: D3D12 Release 6, Build rev 2., 19H1
f1_keywords:
 - D3D12DDI_VARIABLE_SHADING_RATE_TIER
 - d3d12umddi/D3D12DDI_VARIABLE_SHADING_RATE_TIER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VARIABLE_SHADING_RATE_TIER
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_VARIABLE_SHADING_RATE_TIER enumeration


## -description

Indicates the tier at which variable rate shading occurs.

*Variable rate shading* is a mechanism to enable allocation of rendering performance and power at varying rates across the rendered image.

## -enum-fields

### -field D3D12DDI_VARIABLE_SHADING_RATE_TIER_NOT_SUPPORTED

Variable rate shading is not supported.

### -field D3D12DDI_VARIABLE_SHADING_RATE_TIER_1

Variable rate shading is supported at tier 1.

### -field D3D12DDI_VARIABLE_SHADING_RATE_TIER_2

Variable rate shading is supported at tier 2.

## -remarks

The following capabilities are defined for each tier.

**Tier 1**

* Shading rate can only be specified on a per-draw-basis; nothing more granular than that.
* Shading rate applies uniformly to what is drawn independently of where it lies within the render target.

**Tier 2**

* Shading rate can be specified on a per-draw-basis, as in Tier 1. It can also be specified by a combination of per-draw-basis, and of:

    * Semantic from the per-provoking-vertex, and
    * a screen space image

* Shading rates from the three sources are combined using a set of combiners.
* Screen space image tile size is 16x16 or smaller.
* Shading rate requested by the app is guaranteed to be delivered exactly  (for precision of temporal and other reconstruction filters).
* SV_ShadingRate PS input is supported, where SV_ShadingRate provides more info about the shading rate.
* The per-provoking vertex rate, also referred to as per-primitive rate, is only valid when one viewport is used and SV_ViewportIndex is not written to.

## -see-also

