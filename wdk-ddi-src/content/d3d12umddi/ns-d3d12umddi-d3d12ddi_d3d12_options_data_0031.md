---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0031
title: D3D12DDI_D3D12_OPTIONS_DATA_0031 (d3d12umddi.h)
description: Display options data.
old-location: display\d3d12ddi-d3d12-options-data-0031.htm
ms.assetid: 3e60f42a-ea95-4876-b370-5c2f0585dc97
ms.date: 04/16/2018
ms.keywords: D3D12DDI_D3D12_OPTIONS_DATA_0031, D3D12DDI_D3D12_OPTIONS_DATA_0031 structure [Display Devices], d3d12umddi/D3D12DDI_D3D12_OPTIONS_DATA_0031, display.d3d12ddi-d3d12-options-data-0031
f1_keywords:
 - "d3d12umddi/D3D12DDI_D3D12_OPTIONS_DATA_0031"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_D3D12_OPTIONS_DATA_0031
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0031
---

# D3D12DDI_D3D12_OPTIONS_DATA_0031 structure


## -description


Display options data.


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

Copy queue timestamp queries are supported.

## -remarks

For UMDs that support the 0031 (or greater) DDI build, the runtime will query whether the UMD supports timestamps queries on the Copy Queue.

The core runtime will fail if [CreateQueryHeap](nc-d3d12umddi-pfnd3d12ddi_create_query_heap_0001.md) fails for D3D12_QUERY_HEAP_TYPE_COPY_QUEUE_TIMESTAMP in [D3D12DDI_QUERY_HEAP_TYPE](ne-d3d12umddi-d3d12ddi_query_heap_type.md) when the driver has not reported support.

The core runtime will no longer remove the command list in response to EndQuery or [ResolveQueryData](nc-d3d12umddi-pfnd3d12ddi_resolve_query_data.md), that is being called on a Copy command list. The debug layer will have a warning, however, if:

* A COPY_QUEUE_TIMESTAMP query is issued/resolved on a COPY command list when the UMD has not set the CAP indicating support.
* A COPY_QUEUE_TIMESTAMP query is issued/resolved on a command list type other than COPY.

The runtime allows ID3D12CommandQueue::GetClockCalibration/GetTimestampFrequency on Copy command queues when the capability are set. This API should return timestamps that correspond to what the Copy engine will emit, which in turn should be on the same GPU timeline/frequency with what the existing 3D/Compute engines emit.
