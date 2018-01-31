---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
title: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
author: windows-driver-content
description: Video process transform.
old-location: display\d3d12ddi-video-process-transform-0032.htm
old-project: display
ms.assetid: 7c2393e6-3e1b-4b4a-b6ea-5848c38440b0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032, display.d3d12ddi-video-process-transform-0032, D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
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
-	D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
---

# D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure


## -description


Video process transform.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 {
  D3D12DDI_RECT                            SourceRectangle;
  D3D12DDI_RECT                            DestinationRectangle;
  D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020  Orientation;
} D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032, D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032;
````


## -struct-fields




#### - SourceRectangle

Source rectangle.


#### - DestinationRectangle

Destination rectangle.


#### - Orientation

Orientation.

