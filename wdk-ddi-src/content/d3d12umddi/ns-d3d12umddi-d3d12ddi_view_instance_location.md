---
UID: NS:d3d12umddi.D3D12DDI_VIEW_INSTANCE_LOCATION
title: D3D12DDI_VIEW_INSTANCE_LOCATION
author: windows-driver-content
description: View instance location.
old-location: display\d3d12ddi-view-instance-location.htm
old-project: display
ms.assetid: 1b31ac34-233b-4246-a1c3-d0aac0f35db6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3d12umddi/D3D12DDI_VIEW_INSTANCE_LOCATION, D3D12DDI_VIEW_INSTANCE_LOCATION, display.d3d12ddi-view-instance-location, D3D12DDI_VIEW_INSTANCE_LOCATION structure [Display Devices]
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
-	D3D12DDI_VIEW_INSTANCE_LOCATION
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIEW_INSTANCE_LOCATION
---

# D3D12DDI_VIEW_INSTANCE_LOCATION structure


## -description


View instance location.


## -syntax


````
typedef struct _D3D12DDI_VIEW_INSTANCE_LOCATION {
  UINT  ViewportArrayIndex;
  UINT  RenderTargetArrayIndex;
} D3D12DDI_VIEW_INSTANCE_LOCATION, D3D12DDI_VIEW_INSTANCE_LOCATION;
````


## -struct-fields




### -field ViewportArrayIndex

Viewport array index.


### -field RenderTargetArrayIndex

Render target array index.

