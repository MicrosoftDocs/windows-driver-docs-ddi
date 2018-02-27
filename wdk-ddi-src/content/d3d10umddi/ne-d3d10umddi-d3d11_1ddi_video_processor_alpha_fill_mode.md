---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE
title: D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE
author: windows-driver-content
description: Specifies the alpha fill mode for video processing.
old-location: display\d3d11_1ddi_video_processor_alpha_fill_mode.htm
old-project: display
ms.assetid: 22b50f49-821a-407e-89c0-fe7d637664fa
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_BACKGROUND, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_DESTINATION, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE, D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_BACKGROUND, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_DESTINATION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM, display.d3d11_1ddi_video_processor_alpha_fill_mode
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
-	D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE
---

# D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE enumeration


## -description


Specifies the alpha fill mode for video processing.


## -syntax


````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE { 
  D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE         = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_BACKGROUND     = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_DESTINATION    = 2,
  D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM  = 3
} D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE;
````


## -enum-fields




### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE

Alpha values inside the target rectangle are set to opaque. 




### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_BACKGROUND

Alpha values inside the target rectangle are set to the alpha value specified in the background color. To set the background color, call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor.md">VideoProcessorSetOutputBackgroundColor</a> function.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_DESTINATION

Existing alpha values remain unchanged in the output surface.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM

Alpha values are taken from an input stream, scaled, and copied to the corresponding destination rectangle for that stream. The input stream is specified in the <i>StreamIndex</i> parameter of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a> function.

If the input stream does not have alpha data, the video processor sets the alpha values in the target rectangle to opaque. If the input stream is disabled or the source rectangle is empty, the alpha values in the target rectangle are not modified.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputbackgroundcolor.md">VideoProcessorSetOutputBackgroundColor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

