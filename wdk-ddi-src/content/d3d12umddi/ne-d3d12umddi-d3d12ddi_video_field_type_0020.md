---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_FIELD_TYPE_0020
title: D3D12DDI_VIDEO_FIELD_TYPE_0020
author: windows-driver-content
description: Contains values that define how a video frame is interlaced.
old-location: display\d3d12ddi_video_field_type.htm
old-project: display
ms.assetid: 869BF62F-C8FE-4AD8-A413-65FBE97EE7FB
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST, display.d3d12ddi_video_field_type, d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST, D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST, d3d12umddi/D3D12DDI_VIDEO_FIELD_TYPE_0020, D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST, D3D12DDI_VIDEO_FIELD_TYPE_0020, D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE, D3D12DDI_VIDEO_FIELD_TYPE_0020 enumeration [Display Devices]
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
-	D3D12DDI_VIDEO_FIELD_TYPE_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_FIELD_TYPE_0020
---

# D3D12DDI_VIDEO_FIELD_TYPE_0020 enumeration


## -description


Contains values that define how a video frame is interlaced.


## -syntax


````
typedef enum D3D12DDI_VIDEO_FIELD_TYPE_0020 { 
  D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE                           = 0,
  D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST     = 1,
  D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST  = 2
} D3D12DDI_VIDEO_FIELD_TYPE_0020;
````


## -enum-fields




### -field D3D12DDI_VIDEO_FIELD_TYPE_0020_NONE

Frame is progressive.


### -field D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_TOP_FIELD_FIRST

Frame is interlaced. The top field of each frame is displayed first. 


### -field D3D12DDI_VIDEO_FIELD_TYPE_0020_INTERLACED_BOTTOM_FIELD_FIRST

Frame is interlaced. The bottom field of each frame is displayed first.

