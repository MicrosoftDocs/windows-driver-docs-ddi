---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0089
tech.root: display
title: D3D12DDI_D3D12_OPTIONS_DATA_0089
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_D3D12_OPTIONS_DATA_0089 structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0089
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_D3D12_OPTIONS_DATA_0089
f1_keywords:
 - D3D12DDI_D3D12_OPTIONS_DATA_0089
 - d3d12umddi/D3D12DDI_D3D12_OPTIONS_DATA_0089
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_D3D12_OPTIONS_DATA_0089
---

## -description

The **D3D12DDI_D3D12_OPTIONS_DATA_0089** structure describes the feature options supported by the driver/hardware.

## -struct-fields

### -field ResourceBindingTier

The [**D3D12DDI_RESOURCE_BINDING_TIER**](ne-d3d12umddi-d3d12ddi_resource_binding_tier.md) value that identifies the [hardware tier level](/windows/win32/direct3d12/hardware-support) that the driver supports.

### -field ConservativeRasterizationTier

The [**D3D12_CONSERVATIVE_RASTERIZATION_TIER**](ne-d3d12umddi-d3d12ddi_conservative_rasterization_tier.md) value that identifies the supported tier level of conservative rasterization.

### -field TiledResourcesTier

The [**D3D12DDI_TILED_RESOURCES_TIER**](ne-d3d12umddi-d3d12ddi_tiled_resources_tier.md) value that identifies the tier level at which tiled resources are supported.

### -field CrossNodeSharingTier

The [**D3D12DDI_CROSS_NODE_SHARING_TIER**](ne-d3d12umddi-d3d12ddi_cross_node_sharing_tier.md
) value indicating the level of sharing across nodes of a display adapter.

### -field VPAndRTArrayIndexFromAnyShaderFeedingRasterizerSupportedWithoutGSEmulation

Set TRUE when the viewport and render target array index from any shader feeding rasterizer is supported without geometry shader emulation; otherwise, set FALSE.

### -field OutputMergerLogicOp

Set TRUE when output merger logic operations are supported; otherwise, set FALSE.

### -field ResourceHeapTier

The [**D3D12DDI_RESOURCE_HEAP_TIER**](./ne-d3d12umddi-d3d12ddi_resource_heap_tier.md) value that indicates the resource heap tier supported by the driver and hardware.

### -field DepthBoundsTestSupported

Set TRUE when depth bounds testing is supported; otherwise, set FALSE.

### -field ProgrammableSamplePositionsTier

The [**D3D12DDI_PROGRAMMABLE_SAMPLE_POSITIONS_TIER**](ne-d3d12umddi-d3d12ddi_programmable_sample_positions_tier.md) value indicating the supported programmable sample positions tier.

### -field CopyQueueTimestampQueriesSupported

Set TRUE when queue timestamp queries are supported; otherwise, set FALSE.

### -field WriteBufferImmediateQueueFlags

The [**D3D12DDI_COMMAND_QUEUE_FLAGS**](ne-d3d12umddi-d3d12ddi_command_queue_flags.md) value that identifies the flags for the command queue.

### -field ViewInstancingTier

The [**D3D12DDI_VIEW_INSTANCING_TIER**](./ne-d3d12umddi-d3d12ddi_view_instancing_tier.md) value that indicates the supported view instancing tier.

### -field BarycentricsSupported

Set TRUE when Barycentric coordinates are supported; otherwise, set FALSE.

### -field ReservedBufferPlacementSupported

Set TRUE when buffer placement is supported (only 64KB aligned MSAA support); otherwise, set FALSE.

### -field Deterministic64KBUndefinedSwizzle

Set TRUE when deterministic 64KB undefined swizzle is supported; otherwise, set FALSE.

### -field SRVOnlyTiledResourceTier3

Set TRUE when the hardware supports SRV-only sparse volume textures; otherwise, set FALSE.

### -field RenderPassTier

The [**D3D12DDI_RENDER_PASS_TIER**](ne-d3d12umddi-d3d12ddi_render_pass_tier.md) value that indicates render pass tier supported by the driver.

### -field RaytracingTier

The [**D3D12DDI_RAYTRACING_TIER**](ne-d3d12umddi-d3d12ddi_raytracing_tier.md) value that indicates the ray tracing tier supported by the hardware.

### -field VariableShadingRateTier

The [**D3D12DDI_VARIABLE_SHADING_RATE_TIER**](ne-d3d12umddi-d3d12ddi_variable_shading_rate_tier.md) value that indicates the variable shading rate tier that the hardware supports.

### -field PerPrimitiveShadingRateSupportedWithViewportIndexing

Set TRUE when per primitive shading rate is supported with viewport indexing; otherwise, set FALSE.

### -field AdditionalShadingRatesSupported

Set TRUE if additional shading rates are supported; otherwise, set FALSE.

### -field ShadingRateImageTileSize

A UINT value that specifies the tile size of the screen-space image.

### -field BackgroundProcessingSupported

Set TRUE when the driver supports background processing; otherwise, set FALSE.

### -field MeshShaderTier

The [**D3D12DDI_MESH_SHADER_TIER**](./ne-d3d12umddi-d3d12ddi_mesh_shader_tier.md) that the device supports.

### -field SamplerFeedbackTier

The [**D3D12DDI_SAMPLER_FEEDBACK_TIER**](./ne-d3d12umddi-d3d12ddi_mesh_shader_tier.md) that the device supports.

### -field DriverManagedShaderCachePresent

Set TRUE when the driver supports shader cache management; otherwise, set FALSE. When set TRUE, the driver must provide a non-NULL [**PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080**](nc-d3d12umddi-pfnd3d12ddi_implicitshadercachecontrol_0080.md) callback function.

### -field MeshShaderSupportsFullRangeRenderTargetArrayIndex

Set TRUE when the driver supports full render target array indexing; otherwise, set FALSE.

### -field VariableRateShadingSumCombinerSupported

Set TRUE when the driver supports the sum combiner for variable rate shading; otherwise, set FALSE.

### -field MeshShaderPerPrimitiveShadingRateSupported

Set TRUE when the SV_ShadingRate can be set from a mesh shader; otherwise, set FALSE.

### -field MSPrimitivesPipelineStatisticIncludesCulledPrimitives

Set TRUE when the driver supports culled primitives pipeline statistics; otherwise, set FALSE.

### -field EnhancedBarriersSupported

Set TRUE when the driver supports enhanced barriers; otherwise, set FALSE.

## -see-also

[**D3D12DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
