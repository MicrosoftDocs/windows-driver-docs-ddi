---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR (d3d10umddi.h)
description: Sets the background color for the video processor.
old-location: display\videoprocessorsetoutputbackgroundcolor.htm
ms.assetid: F258F21F-0177-4DBB-87FA-F0374689DC7B
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR callback, d3d10umddi/pfnVideoProcessorSetOutputBackgroundColor, display.videoprocessorsetoutputbackgroundcolor, pfnVideoProcessorSetOutputBackgroundColor, pfnVideoProcessorSetOutputBackgroundColor callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTBACKGROUNDCOLOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetOutputBackgroundColor
product:
 - Windows
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

A handle to the video processor object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*YCbCr* [in]

If <b>TRUE</b>, the background color that is specified by the <i>pColor</i> parameter is a YCbCr value. Otherwise, the background color is specified as an RGBA value.

### -param Arg4

*pColor* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color">D3D11_1DDI_VIDEO_COLOR</a> structure that specifies the background color.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_color">D3D11_1DDI_VIDEO_COLOR</a>