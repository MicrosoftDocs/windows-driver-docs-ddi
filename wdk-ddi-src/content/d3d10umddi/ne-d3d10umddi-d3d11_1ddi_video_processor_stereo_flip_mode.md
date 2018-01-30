---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE
title: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE
author: windows-driver-content
description: For stereo 3-D video, specifies whether the data in frame 0 or frame 1 is flipped, either horizontally or vertically.
old-location: display\d3d11_1ddi_video_processor_stereo_flip_mode.htm
old-project: display
ms.assetid: b385a0fd-6181-45c3-ba6e-e292e0b10e68
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d11_1ddi_video_processor_stereo_flip_mode, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME0, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_NONE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME1, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_NONE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME1, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME0
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
-	D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE
---

# D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE enumeration


## -description


For stereo 3-D video, specifies whether the data in frame 0 or frame 1 is flipped, either horizontally or vertically.


## -syntax


````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE { 
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_NONE    = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME0  = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME1  = 2
} D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE;
````


## -enum-fields




### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_NONE

Neither frame is flipped.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME0

The data in frame 0 is flipped.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_FRAME1

The data in frame 1 is flipped.

