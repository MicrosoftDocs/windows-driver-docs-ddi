---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE (d3d10umddi.h)
description: Sets the color space for an input stream on the video processor.
old-location: display\videoprocessorsetstreamcolorspace.htm
ms.assetid: bb187968-ae2a-4872-a745-fb42c0cff528
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE callback, d3d10umddi/pfnVideoProcessorSetStreamColorSpace, display.videoprocessorsetstreamcolorspace, pfnVideoProcessorSetStreamColorSpace, pfnVideoProcessorSetStreamColorSpace callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetStreamColorSpace"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetStreamColorSpace
product:
 - Windows
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE callback function

## -description

Sets the color space for an input stream on the video processor.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*pColorSpace* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_color_space">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a> structure that specifies the color space for the specified input stream.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_color_space">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a>

