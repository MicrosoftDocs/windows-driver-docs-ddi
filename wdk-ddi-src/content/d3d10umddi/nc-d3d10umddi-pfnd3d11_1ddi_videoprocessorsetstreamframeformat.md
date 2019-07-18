---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT (d3d10umddi.h)
description: Specifies whether an input stream on the video processor contains interlaced or progressive frames.
old-location: display\videoprocessorsetstreamframeformat.htm
ms.assetid: 49310ddf-403a-4fb4-98bb-9ef00ef28310
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT callback, d3d10umddi/pfnVideoProcessorSetStreamFrameFormat, display.videoprocessorsetstreamframeformat, pfnVideoProcessorSetStreamFrameFormat, pfnVideoProcessorSetStreamFrameFormat callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetStreamFrameFormat"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoProcessorSetStreamFrameFormat
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT callback function


## -description


Specifies whether an input stream on the video processor contains interlaced or progressive frames.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*Format* [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_frame_format">D3D11_1DDI_VIDEO_FRAME_FORMAT</a> value that specifies the frame format.




## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_frame_format">D3D11_1DDI_VIDEO_FRAME_FORMAT</a>
 

 

