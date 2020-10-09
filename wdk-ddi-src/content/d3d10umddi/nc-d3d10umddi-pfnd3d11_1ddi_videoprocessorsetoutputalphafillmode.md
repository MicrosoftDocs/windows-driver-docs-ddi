---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE (d3d10umddi.h)
description: Sets the alpha fill mode for data that the video processor writes to the render target.
old-location: display\videoprocessorsetoutputalphafillmode.htm
ms.assetid: 0c2cbb8f-d031-4267-b32f-620ed1ad065c
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE callback, d3d10umddi/pfnVideoProcessorSetOutputAlphaFillMode, display.videoprocessorsetoutputalphafillmode, pfnVideoProcessorSetOutputAlphaFillMode, pfnVideoProcessorSetOutputAlphaFillMode callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetOutputAlphaFillMode
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE callback function


## -description

Sets the alpha fill mode for data that the video processor writes to the render target.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*FillMode* [in]

The alpha fill mode, specified as a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_alpha_fill_mode">D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE</a> value. For more information, see the Remarks section.

### -param Arg4

*StreamIndex* [in]

The zero-based index of an input stream. This parameter is used if the <i>AlphaFillMode</i> parameter is set to <b>D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM</b>. Otherwise, the parameter is ignored.

## -remarks

The driver reports its ability to support alpha fill modes in the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL</b> capability, it supports all of the alpha fill modes that are defined by the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_alpha_fill_mode">D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE</a> enumeration. Otherwise, the <i>FillMode</i> parameter must be set to <b>D3D11_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE</b>. 



<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetOutputAlphaFillMode</b> function.</div>
<div> </div>
The default fill mode is <b>D3D11_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview">CreateVideoProcessorInputView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_alpha_fill_mode">D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>