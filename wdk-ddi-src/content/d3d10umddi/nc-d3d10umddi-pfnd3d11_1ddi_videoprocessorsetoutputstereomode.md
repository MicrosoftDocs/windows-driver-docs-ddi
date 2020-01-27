---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE (d3d10umddi.h)
description: Specifies whether the video processor produces stereo video frames.
old-location: display\videoprocessorsetoutputstereomode.htm
ms.assetid: 3e3eaaa6-2725-49de-bca6-df2da1b4324b
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE callback, d3d10umddi/pfnVideoProcessorSetOutputStereoMode, display.videoprocessorsetoutputstereomode, pfnVideoProcessorSetOutputStereoMode, pfnVideoProcessorSetOutputStereoMode callback function [Display Devices]
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetOutputStereoMode"
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
- pfnVideoProcessorSetOutputStereoMode
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE callback function


## -description


Specifies whether the video processor produces stereo video frames.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*Enable* [in]

If <b>TRUE</b>, stereo output is enabled. Otherwise, the video processor produces mono video frames.



## -remarks



By default, the video processor produces mono video frames. If stereo video is enabled, the stereo output format is set through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a> function.



The driver reports its ability to support stereo video modes through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, it can be enabled or disabled to produce stereo video frames.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetOutputStereoMode</b> function.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a>
 

 

