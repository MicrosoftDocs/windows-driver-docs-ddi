---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_BARRIER_FLAGS
title: D3D12DDI_RESOURCE_BARRIER_FLAGS
author: windows-driver-content
description: Contains resource barrier flags.
old-location: display\d3d12ddi_resource_barrier_flags.htm
old-project: display
ms.assetid: 876ABC9C-F9BE-480F-8641-AE132840F8D5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_RESOURCE_BARRIER_FLAGS, D3D12DDI_RESOURCE_BARRIER_FLAGS
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
req.alt-api: D3D12DDI_RESOURCE_BARRIER_FLAGS
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D12DDI_RESOURCE_BARRIER_FLAGS
---

# D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration



## -description
Contains resource barrier flags.



## -syntax

````
typedef enum D3D12DDI_RESOURCE_BARRIER_FLAGS { 
  D3D12DDI_RESOURCE_BARRIER_FLAG_NONE              = 0x0,
  D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY        = 0x1,
  D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY          = 0x2,
  D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY  = 0x4,
  D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING     = 0x8
} D3D12DDI_RESOURCE_BARRIER_FLAGS;
````


## -enum-fields

### -field D3D12DDI_RESOURCE_BARRIER_FLAG_NONE

No flag value.


### -field D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY

Indicates a release. This flag is relevant only for ranged barriers.


### -field D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY

Indicates an acquire. This flag is relevant only for ranged barriers.


### -field D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY

Indicates that ranged barriers are associated with a parameter of an atomic copy operation. 


### -field D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING

Indicates that an aliasing barrier has been converted to a ranged barrier.


## -remarks
The absence of both <b>D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY</b> and <b>D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY</b> denotes both an acquire and release.

During an acquire, GPU caches may need to be explicitly invalidated. During a release, GPU caches may need to be explicitly flushed. </p>