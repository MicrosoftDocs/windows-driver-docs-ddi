---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_FRAME_FORMAT
title: D3D11_1DDI_VIDEO_FRAME_FORMAT
author: windows-driver-content
description: Describes how a video stream is interlaced.
old-location: display\d3d11_1ddi_video_frame_format.htm
old-project: display
ms.assetid: 36af5af2-dfb1-4827-8898-93e52f4c8312
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 1, 3, A, D, D3D11_1DDI_VIDEO_FRAME_FORMAT, D3D11_1DDI_VIDEO_FRAME_FORMAT enumeration [Display Devices], D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE, E, F, I, M, O, R, T, V, _, d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT, d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST, d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST, d3d10umddi/D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE, display.d3d11_1ddi_video_frame_format"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_FRAME_FORMAT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_FRAME_FORMAT
---

# D3D11_1DDI_VIDEO_FRAME_FORMAT enumeration


## -description


Describes how a video stream is interlaced.


## -syntax


````
typedef enum D3D11_1DDI_VIDEO_FRAME_FORMAT { 
  D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE                    = 0,
  D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST     = 1,
  D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST  = 2
} D3D11_1DDI_VIDEO_FRAME_FORMAT;
````


## -enum-fields




### -field D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE

Frames are progressive.


### -field D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST

Frames are interlaced. The top field of each frame is displayed first.


### -field D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST

Frame are interlaced. The bottom field of each frame is displayed first.

