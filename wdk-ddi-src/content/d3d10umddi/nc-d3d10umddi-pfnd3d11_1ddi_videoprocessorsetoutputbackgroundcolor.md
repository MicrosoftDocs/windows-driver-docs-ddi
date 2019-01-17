---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR
description: Sets the background color for the video processor.
old-location: display\videoprocessorsetoutputbackgroundcolor.htm
ms.assetid: F258F21F-0177-4DBB-87FA-F0374689DC7B
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR callback, d3d10umddi/pfnVideoProcessorSetOutputBackgroundColor, display.videoprocessorsetoutputbackgroundcolor, pfnVideoProcessorSetOutputBackgroundColor, pfnVideoProcessorSetOutputBackgroundColor callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoProcessorSetOutputBackgroundColor
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR callback function


## -description


Sets the background color for the video processor.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function.

### -param Arg3

*YCbCr* [in]

If <b>TRUE</b>, the background color that is specified by the <i>pColor</i> parameter is a YCbCr value. Otherwise, the background color is specified as an RGBA value.

### -param *

*pColor* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406454">D3D11_1DDI_VIDEO_COLOR</a> structure that specifies the background color.




## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406454">D3D11_1DDI_VIDEO_COLOR</a>
 

 

