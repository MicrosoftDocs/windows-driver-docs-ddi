---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
title: D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
author: windows-driver-content
description: Describes operations that the video processor can perform more efficiently than VideoProcessorBlt.
old-location: display\d3dwddm2_0ddi_video_processor_behavior_hints.htm
old-project: display
ms.assetid: 1D995AE5-C856-4971-8D51-B06EB32F8C74
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS, D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
req.alt-loc: D3d10umddi.h
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
req.typenames: D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
---

# D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS enumeration



## -description
Describes operations that the video processor can perform more efficiently than <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>.



## -syntax

````
typedef enum D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS { 
  D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_ROTATION                = 0x01,
  D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_RESIZE                  = 0x02,
  D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_COLOR_SPACE_CONVERSION  = 0x04
} D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS;
````


## -enum-fields

### -field D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_ROTATION

Indicates that multi-plane overlay hardware can perform the rotation operation more efficiently than <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>. 


### -field D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_RESIZE

Indicates that the multi-plane overlay hardware can perform the scaling operation more efficiently than <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>. 


### -field D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_COLOR_SPACE_CONVERSION

Indicates that the multi-plane overlay hardware can perform the colorspace conversion operation more efficiently than <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

