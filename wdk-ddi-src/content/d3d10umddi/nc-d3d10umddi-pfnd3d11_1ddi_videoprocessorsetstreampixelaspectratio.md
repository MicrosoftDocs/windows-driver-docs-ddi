---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO (d3d10umddi.h)
description: Sets the pixel aspect ratio for an input stream on the video processor.
old-location: display\videoprocessorsetstreampixelaspectratio.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO callback, d3d10umddi/pfnVideoProcessorSetStreamPixelAspectRatio, display.videoprocessorsetstreampixelaspectratio, pfnVideoProcessorSetStreamPixelAspectRatio, pfnVideoProcessorSetStreamPixelAspectRatio callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetStreamPixelAspectRatio
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO callback function


## -description

Sets the pixel aspect ratio for an input stream on the video processor.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*Enable* [in]

If <b>TRUE</b>, the <i>pSourceRatio</i> and <i>pDestinationRatio</i> parameters contain valid values. Otherwise, the pixel aspect ratios are unspecified.

### -param Arg5

*pSourceRatio* [in]

A pointer to a <b>DXGI_RATIONAL</b> structure that contains the pixel aspect ratio of the source rectangle. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter can be NULL.

</div>
<div> </div>

### -param Arg6

*pDestRatio* [in]

A pointer to a <b>DXGI_RATIONAL</b> structure that contains the pixel aspect ratio of the destination rectangle. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter can be NULL.

</div>
<div> </div>

## -remarks

Pixel aspect ratios of the form 0/<i>n</i> and <i>n</i>/0 are not valid.



The default pixel aspect ratio is 1:1 (square pixels).



The driver reports its ability to support the pixel aspect ratio capability in the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO </b> capability, the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamalpha">VideoProcessorSetStreamAlpha</a> can be called to set the pixel aspect ratios for an input stream of the video processor.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO </b> capability, the Microsoft Direct3D runtime does not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamalpha">VideoProcessorSetStreamAlpha</a> function.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>
