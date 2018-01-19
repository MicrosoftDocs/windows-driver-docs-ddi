---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0033
title: D3D12DDI_D3D12_OPTIONS_DATA_0033
author: windows-driver-content
description: Display options data.
old-location: display\d3d12ddi-d3d12-options-data-0033.htm
old-project: display
ms.assetid: d2b90ec1-cc4c-4a2b-8f7e-d46cd39d553b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_D3D12_OPTIONS_DATA_0033, D3D12DDI_D3D12_OPTIONS_DATA_0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_D3D12_OPTIONS_DATA_0033
req.alt-loc: d3d12umddi.h
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
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0033
---

# D3D12DDI_D3D12_OPTIONS_DATA_0033 structure



## -description
Display options data.



## -syntax

````
typedef struct _D3D12DDI_D3D12_OPTIONS_DATA_0033 {
  D3D12DDI_RESOURCE_BINDING_TIER               ResourceBindingTier;
  D3D12DDI_CONSERVATIVE_RASTERIZATION_TIER     ConservativeRasterizationTier;
  D3D12DDI_TILED_RESOURCES_TIER                TiledResourcesTier;
  D3D12DDI_CROSS_NODE_SHARING_TIER             CrossNodeSharingTier;
  BOOL                                         VPAndRTArrayIndexFromAnyShaderFeedingRasterizerSupportedWithoutGSEmulation;
  BOOL                                         OutputMergerLogicOp;
  D3D12DDI_RESOURCE_HEAP_TIER                  ResourceHeapTier;
  BOOL                                         DepthBoundsTestSupported;
  D3D12DDI_PROGRAMMABLE_SAMPLE_POSITIONS_TIER  ProgrammableSamplePositionsTier;
  BOOL                                         CopyQueueTimestampQueriesSupported;
  D3D12DDI_COMMAND_QUEUE_FLAGS                 WriteBufferImmediateQueueFlags;
  D3D12DDI_VIEW_INSTANCING_TIER                ViewInstancingTier;
  BOOL                                         BarycentricsSupported;
} D3D12DDI_D3D12_OPTIONS_DATA_0033, D3D12DDI_D3D12_OPTIONS_DATA_0033;
````


## -struct-fields

### -field ResourceBindingTier

Resource binding tier.


### -field ConservativeRasterizationTier

Conservative rasterization tier.


### -field TiledResourcesTier

Tiled resource tier.


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


## -remarks
