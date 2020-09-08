---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE (d3d10umddi.h)
description: Sets the color-palette entries for an input stream on the video processor.
old-location: display\videoprocessorsetstreampalette.htm
ms.assetid: a655baef-4f99-45a1-ac78-5f54d2f4f1ab
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE callback, d3d10umddi/pfnVideoProcessorSetStreamPalette, display.videoprocessorsetstreampalette, pfnVideoProcessorSetStreamPalette, pfnVideoProcessorSetStreamPalette callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetStreamPalette
product:
 - Windows
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE callback function


## -description

Sets the color-palette entries for an input stream on the video processor.

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

*Count* [in]

The number of elements in the array that is referenced by the <i>pEntries</i> parameter.

### -param Arg5

*pEntries* [in]

A pointer to an array of palette entries. For RGB streams, the palette entries are specified in the <b>DXGI_FORMAT_B8G8R8A8</b> format. For YCbCr streams, the palette entries are specified in the <b>DXGI_FORMAT_AYUV</b> format.

## -remarks

The <b>VideoProcessorSetStreamPalette</b> function is called only for input streams that have a palettized color format. Palettized formats with 4 bits per pixel (bpp) use the first 16 entries in the list. Formats with 8 bpp use the first 256 entries.



If a pixel has a palette index greater than the number of entries, the device treats the pixel as white with opaque alpha. For full-range RGB, this value is (255, 255, 255, 255); for YCbCr the value is (255, 235, 128, 128).



The driver reports its ability to support palettized color formats in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability, it can be configured with color-palette entries for an input stream.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability, the Microsoft Direct3D runtime does not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode">VideoProcessorSetOutputStereoMode</a> function.</div>
<div> </div>
If the driver does not report the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability, every palette entry must have an alpha value of 0xFF (opaque).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>

