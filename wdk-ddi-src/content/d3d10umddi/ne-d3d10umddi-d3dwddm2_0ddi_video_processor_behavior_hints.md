---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
title: D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS (d3d10umddi.h)
description: Describes operations that the video processor can perform more efficiently than VideoProcessorBlt.
old-location: display\d3dwddm2_0ddi_video_processor_behavior_hints.htm
ms.assetid: 1D995AE5-C856-4971-8D51-B06EB32F8C74
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS enumeration"]
ms.keywords: D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS, D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS enumeration [Display Devices], D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_COLOR_SPACE_CONVERSION, D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_RESIZE, D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_ROTATION, d3d10umddi/D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS, d3d10umddi/D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_COLOR_SPACE_CONVERSION, d3d10umddi/D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_RESIZE, d3d10umddi/D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_ROTATION, display.d3dwddm2_0ddi_video_processor_behavior_hints
f1_keywords:
 - "d3d10umddi/D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS
---

# D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINTS enumeration


## -description


Describes operations that the video processor can perform more efficiently than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>.


## -enum-fields




### -field D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_ROTATION

Indicates that multi-plane overlay hardware can perform the rotation operation more efficiently than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>. 


### -field D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_RESIZE

Indicates that the multi-plane overlay hardware can perform the scaling operation more efficiently than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>. 


### -field D3DWDDM2_0DDI_VIDEO_PROCESSOR_BEHAVIOR_HINT_MULTIPLANE_OVERLAY_COLOR_SPACE_CONVERSION

Indicates that the multi-plane overlay hardware can perform the color space conversion operation more efficiently than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>
 

 

