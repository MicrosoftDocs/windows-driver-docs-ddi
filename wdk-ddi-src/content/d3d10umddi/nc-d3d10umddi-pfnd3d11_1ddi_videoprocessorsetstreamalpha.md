---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA (d3d10umddi.h)
description: Sets the planar alpha for an input stream on the video processor.
old-location: display\videoprocessorsetstreamalpha.htm
ms.assetid: 9208bcd7-c030-4c2f-b3bc-e1bff3839cef
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA callback, d3d10umddi/pfnVideoProcessorSetStreamAlpha, display.videoprocessorsetstreamalpha, pfnVideoProcessorSetStreamAlpha, pfnVideoProcessorSetStreamAlpha callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetStreamAlpha"
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
- pfnVideoProcessorSetStreamAlpha
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA callback function


## -description


Sets the planar alpha for an input stream on the video processor.




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

*Enable* [in]

If <b>TRUE</b>, alpha blending is to be enabled on the video processor.

### -param Arg5

*Alpha* [in]

A pointer to a <b>FLOAT</b> value that specifies the planar alpha value. The value can range from 0.0 (transparent) to 1.0 (opaque). 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is <b>FALSE</b>, this parameter is ignored.

</div>
<div> </div>



## -remarks



By default, alpha blending is disabled. 



For each pixel, the destination color value is computed as follows:

<code>Cd = Cs * (As * Ap * Ae) + Cd * (1.0 - As * Ap * Ae)</code>

where:

<ul>
<li><code>Cd</code> = The color value of the destination pixel</li>
<li><code>Cs</code> = The color value of the source pixel</li>
<li><code>As</code> = The per-pixel source alpha</li>
<li><code>Ap</code> = The planar alpha value</li>
<li><code>Ae</code> = The palette-entry alpha value, or 1.0 </li>
</ul>
<div class="alert"><b>Note</b>  Palette-entry alpha values apply only to palettized color formats, and only when the device advertises support for the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. Otherwise, this factor equals 1.0.</div>
<div> </div>
The destination alpha value is computed according to the alpha fill mode. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode">VideoProcessorSetOutputAlphaFillMode</a>


The driver reports its ability to support stereo alpha blending for an input stream in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM </b> capability, it can be enabled or disabled to produce stereo video frames.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetStreamAlpha</b> function.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode">VideoProcessorSetOutputAlphaFillMode</a>
 

 

