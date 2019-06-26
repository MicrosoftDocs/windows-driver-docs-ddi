---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE
title: D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE (d3d10umddi.h)
description: Specifies the alpha fill mode for video processing.
old-location: display\d3d11_1ddi_video_processor_alpha_fill_mode.htm
ms.assetid: 22b50f49-821a-407e-89c0-fe7d637664fa
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_BACKGROUND, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_DESTINATION, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_BACKGROUND, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_DESTINATION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM, display.d3d11_1ddi_video_processor_alpha_fill_mode
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE
---

# D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE enumeration


## -description


Specifies the alpha fill mode for video processing.


## -enum-fields




### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE

Alpha values inside the target rectangle are set to opaque. 




### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_BACKGROUND

Alpha values inside the target rectangle are set to the alpha value specified in the background color. To set the background color, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor">VideoProcessorSetOutputBackgroundColor</a> function.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_DESTINATION

Existing alpha values remain unchanged in the output surface.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM

Alpha values are taken from an input stream, scaled, and copied to the corresponding destination rectangle for that stream. The input stream is specified in the <i>StreamIndex</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode">VideoProcessorSetOutputAlphaFillMode</a> function.

If the input stream does not have alpha data, the video processor sets the alpha values in the target rectangle to opaque. If the input stream is disabled or the source rectangle is empty, the alpha values in the target rectangle are not modified.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode">VideoProcessorSetOutputAlphaFillMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor">VideoProcessorSetOutputBackgroundColor</a>
 

 

