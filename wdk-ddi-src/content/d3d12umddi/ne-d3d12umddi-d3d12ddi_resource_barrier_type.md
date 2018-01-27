---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_BARRIER_TYPE
title: D3D12DDI_RESOURCE_BARRIER_TYPE
author: windows-driver-content
description: Specifies the type of resource barrier.
old-location: display\d3d12ddi_resource_barrier_type.htm
old-project: display
ms.assetid: 3865DB8A-A920-42AC-B802-E5A3FB02014C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_RESOURCE_BARRIER_TYPE, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_TYPE_0022_RANGED, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_TYPE_UAV, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_TYPE, D3D12DDI_RESOURCE_BARRIER_TYPE_TRANSITION, D3D12DDI_RESOURCE_BARRIER_TYPE_UAV, D3D12DDI_RESOURCE_BARRIER_TYPE_0022_RANGED, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_TYPE_TRANSITION, D3D12DDI_RESOURCE_BARRIER_TYPE enumeration [Display Devices], display.d3d12ddi_resource_barrier_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	D3d12umddi.h
apiname: 
-	D3D12DDI_RESOURCE_BARRIER_TYPE
product: Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_BARRIER_TYPE
---

# D3D12DDI_RESOURCE_BARRIER_TYPE enumeration


## -description


Specifies the type of resource barrier.


## -syntax


````
typedef enum D3D12DDI_RESOURCE_BARRIER_TYPE { 
  D3D12DDI_RESOURCE_BARRIER_TYPE_TRANSITION,
  D3D12DDI_RESOURCE_BARRIER_TYPE_UAV,
  D3D12DDI_RESOURCE_BARRIER_TYPE_0022_RANGED
} D3D12DDI_RESOURCE_BARRIER_TYPE;
````


## -enum-fields




### -field D3D12DDI_RESOURCE_BARRIER_TYPE_TRANSITION

A transition barrier that indicates a transition of a set of subresources between different usages. 


### -field D3D12DDI_RESOURCE_BARRIER_TYPE_ALIASING



### -field D3D12DDI_RESOURCE_BARRIER_TYPE_UAV

An unordered access view (UAV) barrier that indicates all UAV accesses to a resource must complete before any future UAV accesses can begin.


### -field D3D12DDI_RESOURCE_BARRIER_TYPE_0022_RANGED

A ranged resource barrier.

