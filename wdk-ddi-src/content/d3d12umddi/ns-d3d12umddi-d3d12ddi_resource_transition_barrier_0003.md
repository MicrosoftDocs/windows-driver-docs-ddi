---
UID: NS:d3d12umddi.D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
title: D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
author: windows-driver-content
description: Describes a transition barrier between subresources.
old-location: display\d3d12ddi_resource_transition_barrier_0003.htm
old-project: display
ms.assetid: 86E2A0A4-F02C-43E7-8CC1-395B444299A6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 structure [Display Devices], D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003, d3d12umddi/D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003, display.d3d12ddi_resource_transition_barrier_0003
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
product: Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
---

# D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 structure


## -description


Describes a transition barrier between subresources.


## -syntax


````
typedef struct D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 {
  D3D12DDI_HRESOURCE       hResource;
  UINT                     Subresource;
  D3D12DDI_RESOURCE_STATES StateBefore;
  D3D12DDI_RESOURCE_STATES StateAfter;
} D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003;
````


## -struct-fields




### -field hResource

The handle of a resource.


### -field Subresource

A subresource.


### -field StateBefore

The state before a transition.


### -field StateAfter

The state after a transition.

