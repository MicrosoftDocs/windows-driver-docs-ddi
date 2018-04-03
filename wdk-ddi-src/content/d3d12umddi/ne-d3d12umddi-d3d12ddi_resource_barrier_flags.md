---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_BARRIER_FLAGS
title: D3D12DDI_RESOURCE_BARRIER_FLAGS
author: windows-driver-content
description: Contains resource barrier flags.
old-location: display\d3d12ddi_resource_barrier_flags.htm
old-project: display
ms.assetid: 876ABC9C-F9BE-480F-8641-AE132840F8D5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_RESOURCE_BARRIER_FLAGS, D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration [Display Devices], D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING, D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY, D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY, D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY, D3D12DDI_RESOURCE_BARRIER_FLAG_NONE, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAGS, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ALIASING, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_0022_ATOMIC_COPY, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_BEGIN_ONLY, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_END_ONLY, d3d12umddi/D3D12DDI_RESOURCE_BARRIER_FLAG_NONE, display.d3d12ddi_resource_barrier_flags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_RESOURCE_BARRIER_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_BARRIER_FLAGS
---

# D3D12DDI_RESOURCE_BARRIER_FLAGS enumeration


## -description


Contains resource barrier flags.


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

During an acquire, GPU caches may need to be explicitly invalidated. During a release, GPU caches may need to be explicitly flushed. 



