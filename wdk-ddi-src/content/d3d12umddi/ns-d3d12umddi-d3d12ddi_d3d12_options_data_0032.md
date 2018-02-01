---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0032
title: D3D12DDI_D3D12_OPTIONS_DATA_0032
author: windows-driver-content
description: Display options data.
old-location: display\d3d12ddi-d3d12-options-data-0032.htm
old-project: display
ms.assetid: 23b2a512-9828-4d1c-9282-2df6a1a80d85
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d12ddi-d3d12-options-data-0032, D3D12DDI_D3D12_OPTIONS_DATA_0032 structure [Display Devices], D3D12DDI_D3D12_OPTIONS_DATA_0032, d3d12umddi/D3D12DDI_D3D12_OPTIONS_DATA_0032
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_D3D12_OPTIONS_DATA_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0032
---

# D3D12DDI_D3D12_OPTIONS_DATA_0032 structure


## -description


Display options data.


## -syntax


````
typedef struct _D3D12DDI_D3D12_OPTIONS_DATA_0032 {
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
} D3D12DDI_D3D12_OPTIONS_DATA_0032, D3D12DDI_D3D12_OPTIONS_DATA_0032;
````


## -struct-fields




### -field ResourceBindingTier

Resource binding tier.


### -field ConservativeRasterizationTier

Conservative rasterization tier.


### -field TiledResourcesTier

Tile resources tier.


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

