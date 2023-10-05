---
UID: NE:d3d12umddi.D3D12DDICAPS_TYPE
title: D3D12DDICAPS_TYPE (d3d12umddi.h)
description: Learn more about the D3D12DDICAPS_TYPE enumeration.
old-location: display\d3d12ddicaps_type.htm
ms.date: 03/31/2023
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
req.typenames: D3D12DDICAPS_TYPE
f1_keywords:
 - D3D12DDICAPS_TYPE
 - d3d12umddi/D3D12DDICAPS_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDICAPS_TYPE
---

# D3D12DDICAPS_TYPE enumeration

## -description

**D3D12DDICAPS_TYPE** specifies a capability type in [**D3D12DDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md).

## -enum-fields

### -field D3D12DDICAPS_TYPE_TEXTURE_LAYOUT

Texture layout. Deprecated. Use D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT instead.

### -field D3D12DDICAPS_TYPE_SWIZZLE_PATTERN

Swizzle pattern. Deprecated. Use D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN instead.

### -field D3D12DDICAPS_TYPE_MEMORY_ARCHITECTURE

Memory architecture.

### -field D3D12DDICAPS_TYPE_TEXTURE_LAYOUT_SETS

Texture layout sets.

### -field D3D12DDICAPS_TYPE_SHADER

Shader.

### -field D3D12DDICAPS_TYPE_ARCHITECTURE_INFO

Architecture information.

### -field D3D12DDICAPS_TYPE_D3D12_OPTIONS

Options for D3D12.

### -field D3D12DDICAPS_TYPE_3DPIPELINESUPPORT

The driver provides 3D pipeline support. The driver reports the [**D3D12DDI_3DPIPELINELEVEL**](ne-d3d12umddi-d3d12ddi_3dpipelinelevel.md) value that represents the maximum pipeline level that it supports. Valid returnable feature levels are 12.1 and earlier. The **3DPIPELINESUPPORT1** value is used to query for any feature level, including 12.2 and later. See Remarks.

### -field D3D12DDICAPS_TYPE_GPUVA_CAPS

The driver supports GPU video acceleration capabilities.

### -field D3D12DDICAPS_TYPE_TEXTURE_LAYOUT1

Texture layout. Deprecated. Use D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT instead.

### -field D3D12DDICAPS_TYPE_0011_SHADER_MODELS

Shader models.

### -field D3D12DDICAPS_TYPE_0030_PROTECTED_RESOURCE_SESSION_SUPPORT

Protected resource session support.

### -field D3D12DDICAPS_TYPE_0030_CRYPTO_SESSION_SUPPORT

Crypto session support. Deprecated. See D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_SUPPORT in to [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).

### -field D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES

CPU page table false positives.

### -field D3D12DDICAPS_TYPE_0022_TEXTURE_LAYOUT

Texture layout.

### -field D3D12DDICAPS_TYPE_0022_SWIZZLE_PATTERN

Swizzle pattern.

### -field D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY

User mode driver-based command queue priority.

### -field D3D12DDICAPS_TYPE_0030_CONTENT_PROTECTION_SYSTEM_COUNT

Content protection system count. Deprecated. See D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_COUNT in to [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).

### -field D3D12DDICAPS_TYPE_0030_CONTENT_PROTECTION_SYSTEM_SUPPORT

Content protection system support. Deprecated. See D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_SUPPORT in to [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).

### -field D3D12DDICAPS_TYPE_0030_CRYPTO_SESSION_TRANSFORM_SUPPORT

Crypto transform support. Deprecated. See D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_TRANSFORM_SUPPORT in to [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).

### -field D3D12DDICAPS_TYPE_0033_ADAPTER_COMPUTE_ONLY

Adapter compute only.

### -field D3D12DDICAPS_TYPE_0050_HARDWARE_SCHEDULING_CAPS

Hardware scheduling capabilities.

### -field D3D12DDICAPS_TYPE_QUERY_META_COMMAND_CAPS_0061

Query meta-command capabilities.

### -field D3D12DDICAPS_TYPE_EXECUTECOMMANDLISTS_PARALLELISM

Execute command lists in parallel.

### -field D3D12DDICAPS_TYPE_SAMPLER_FEEDBACK_0073

Supports sampler feedback. See the [Sampler Feedback Specification](https://microsoft.github.io/DirectX-Specs/d3d/SamplerFeedback.html) for more information.

### -field D3D12DDICAPS_TYPE_0073_SUPPORT_BATCHED_MARKERS

Supports batched markers.

### -field D3D12DDICAPS_TYPE_0074_PROTECTED_RESOURCE_SESSION_TYPE_COUNT

Supports protected resource session type count. Starting with D3D12DDI_FEATURE_VERSION_CONTENT_PROTECTION_RESOURCES_0074, this query is made if the driver reports D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAG_SUPPORTED via D3D12DDICAPS_TYPE_PROTECTED_RESOURCE_SESSION_SUPPORT. The driver must report at least 1 GUID for D3D12DDI_PROTECTED_RESOURCES_SESSION_HARDWARE_PROTECTED. See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

### -field D3D12DDICAPS_TYPE_0074_PROTECTED_RESOURCE_SESSION_TYPES

Supports protected resource session types. Starting with D3D12DDI_FEATURE_VERSION_CONTENT_PROTECTION_RESOURCES_0074, this query is made if the driver reports D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAG_SUPPORTED via D3D12DDICAPS_TYPE_PROTECTED_RESOURCE_SESSION_SUPPORT. The driver must report D3D12DDI_PROTECTED_RESOURCES_SESSION_HARDWARE_PROTECTED. Allowed GUIDS are controlled via an allow list and additional GUIDS require approval from Microsoft. See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

### -field D3D12DDICAPS_TYPE_0081_3DPIPELINESUPPORT1

Support for 3D pipeline; [**pData**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md) points to a [**D3D12DDI_3DPIPELINESUPPORT1_DATA_0081**](ns-d3d12umddi-d3d12ddi_3dpipelinesupport1_data_0081.md) structure. The driver reports the [**D3D12DDI_3DPIPELINELEVEL**](ne-d3d12umddi-d3d12ddi_3dpipelinelevel.md) value that represents the maximum feature level that it supports in the **MaximumDriverSupportedFeatureLevel** field. See Remarks.

### -field D3D12DDICAPS_TYPE_OPTIONS_0090

The driver should indicate support for capabilities in the [**D3D12DDI_OPTIONS_0090**](ns-d3d12umddi-d3d12ddi_options_data_0090.md) structure.

### -field D3D12DDICAPS_TYPE_OPTIONS_0091

The driver should indicate support for capabilities in the [**D3D12DDI_OPTIONS_0091**](ns-d3d12umddi-d3d12ddi_options_data_0091.md) structure.

## -remarks

The Direct3D runtime specifies a **D3DDDICAPS_TYPE_*XXX*** in  [**D3D12DDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md) when it calls a driver's [**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md) callback function.

When determining 3D pipeline support:

* Versions of Direct3D built into the operating system at or before Windows 10, version 20H2 use **3DPIPELINESUPPORT**.
* Versions of Direct3D built into Windows Server 2022 operating system, or organized as a re-distributable, use **3DPIPELINESUPPORT1**, and fall back to 3DPIPELINESUPPORT if it fails.

## -see-also

[**D3D12DDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
