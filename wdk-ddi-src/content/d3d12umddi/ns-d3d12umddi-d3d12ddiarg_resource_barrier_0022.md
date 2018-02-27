---
UID: NS:d3d12umddi.D3D12DDIARG_RESOURCE_BARRIER_0022
title: D3D12DDIARG_RESOURCE_BARRIER_0022
author: windows-driver-content
description: Describes a resource barrier.
old-location: display\d3d12ddiarg_resource_barrier_0022.htm
old-project: display
ms.assetid: ED597BB0-F9ED-4311-9E2F-06AEA2755B37
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDIARG_RESOURCE_BARRIER_0022, D3D12DDIARG_RESOURCE_BARRIER_0022 structure [Display Devices], d3d12umddi/D3D12DDIARG_RESOURCE_BARRIER_0022, display.d3d12ddiarg_resource_barrier_0022
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDIARG_RESOURCE_BARRIER_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_RESOURCE_BARRIER_0022
---

# D3D12DDIARG_RESOURCE_BARRIER_0022 structure


## -description


Describes a resource barrier.


## -syntax


````
typedef struct D3D12DDIARG_RESOURCE_BARRIER_0022 {
  D3D12DDI_RESOURCE_BARRIER_TYPE  Type;
  D3D12DDI_RESOURCE_BARRIER_FLAGS Flags;
  union      {
        D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 Transition;
        D3D12DDI_RESOURCE_UAV_BARRIER             UAV;
        D3D12DDI_RESOURCE_RANGED_BARRIER_0022     Ranged;
    };
} D3D12DDIARG_RESOURCE_BARRIER_0022;
````


## -struct-fields




### -field Type

The type of resource barrier as a <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_resource_barrier_type.md">D3D12DDI_RESOURCE_BARRIER_TYPE</a> value.


### -field Flags

A barrier flag as a <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_resource_barrier_flags.md">D3D12DDI_RESOURCE_BARRIER_FLAGS</a> value.


#### - {
        D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 Transition;
        D3D12DDI_RESOURCE_UAV_BARRIER             UAV;
        D3D12DDI_RESOURCE_RANGED_BARRIER_0022     Ranged;
    }

A resource barrier.

