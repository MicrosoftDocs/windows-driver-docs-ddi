---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
title: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
author: windows-driver-content
description: Video process transform.
old-location: display\d3d12ddi-video-process-transform-0032.htm
tech.root: display
ms.assetid: 7c2393e6-3e1b-4b4a-b6ea-5848c38440b0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032, D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032, display.d3d12ddi-video-process-transform-0032
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
---

# D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure


## -description


Specifies flip, rotation, scale and destination translation for the video input.


## -struct-fields




### -field SourceRectangle

The source rectangle is the portion of the input surface that is blitted to the destination surface. The source rectangle is given in pixel coordinates, relative to the input surface. Stereo Format after orientation is applied.


### -field DestinationRectangle

The destination rectangle is the portion of the output surface that receives the blit for this stream. The destination rectangle is given in pixel coordinates, relative to the output surface.


### -field Orientation

The rotation and flip operation to apply to the source. Source and Destination rectangles are specified in post orientation coordinates.

