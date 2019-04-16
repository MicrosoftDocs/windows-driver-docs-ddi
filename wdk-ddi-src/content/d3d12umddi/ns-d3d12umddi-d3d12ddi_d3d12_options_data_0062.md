---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0062
title: D3D12DDI_D3D12_OPTIONS_DATA_0062
author: windows-driver-content
description: Contains display options data.
tech.root: display
ms.assetid: 16b0ed82-7a84-45ab-8695-f2d2b9a044d4
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
ms.keywords: D3D12DDI_D3D12_OPTIONS_DATA_0062, D3D12DDI_D3D12_OPTIONS_DATA_0062, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0062
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_D3D12_OPTIONS_DATA_0062
product:
- Windows
targetos: Windows
ms.custom: D3D12 Release 6, Build rev 2., 19H1
---

# D3D12DDI_D3D12_OPTIONS_DATA_0062 structure

## -description

Contains display options data.

## -struct-fields

### -field ResourceBindingTier

Resource binding tier.

### -field ConservativeRasterizationTier

Conservative rasterization tier.

### -field TiledResourcesTier

Tiled resources tier.

### -field CrossNodeSharingTier

Cross node sharing tier.

### -field VPAndRTArrayIndexFromAnyShaderFeedingRasterizerSupportedWithoutGSEmulation

VP and RT array index from any shader feeding rasterizer supported without GS emulation.

### -field OutputMergerLogicOp

Output merger logic option.

### -field ResourceHeapTier

Resource heap tier.

### -field DepthBoundsTestSupported

Depth bounds test supported.

### -field ProgrammableSamplePositionsTier

Programmable sample positions tier.

### -field CopyQueueTimestampQueriesSupported

Copy queue timestamp queries supported.

### -field WriteBufferImmediateQueueFlags

Write buffer immediate queue flags.

### -field ViewInstancingTier

View instancing tier.

### -field BarycentricsSupported

Barycentrics supported.

### -field ReservedBufferPlacementSupported

Reserved buffer placement supported. Supports only just 64KB aligned MSAA.

### -field Deterministic64KBUndefinedSwizzle

Deterministic 64KB undefined swizzle.

### -field SRVOnlyTiledResourceTier3

Indicates whether the hardware supports SRV-only sparse volume textures.

### -field RenderPassTier

The [D3D12DDI_RENDER_PASS_TIER](ne-d3d12umddi-d3d12ddi_render_pass_tier.md) that the hardware supports. 

### -field RaytracingTier

The [D3D12DDI_RAYTRACING_TIER](ne-d3d12umddi-d3d12ddi_raytracing_tier.md) that the hardware supports.

### -field VariableShadingRateTier

The [D3D12DDI_VARIABLE_SHADING_RATE_TIER](ne-d3d12umddi-d3d12ddi_variable_shading_rate_tier.md) that the hardware supports.

### -field PerPrimitiveShadingRateSupportedWithViewportIndexing

Indicates that primitive shading rate is supported with viewport indexing.

### -field AdditionalShadingRatesSupported

Indicates that additional shading rates are supported.

### -field ShadingRateImageTileSize

The shading rate image tile size.

### -field BackgroundProcessingSupported
 
BOOL to indicate that the driver supports background processing.

## -remarks

## -see-also
