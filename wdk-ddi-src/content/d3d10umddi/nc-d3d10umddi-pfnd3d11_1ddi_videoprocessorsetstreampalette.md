---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE
author: windows-driver-content
description: Sets the color-palette entries for an input stream on the video processor.
old-location: display\videoprocessorsetstreampalette.htm
old-project: display
ms.assetid: a655baef-4f99-45a1-ac78-5f54d2f4f1ab
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE, d3d10umddi/pfnVideoProcessorSetStreamPalette, display.videoprocessorsetstreampalette, pfnVideoProcessorSetStreamPalette, pfnVideoProcessorSetStreamPalette callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	pfnVideoProcessorSetStreamPalette
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE callback


## -description


Sets the color-palette entries for an input stream on the video processor.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE pfnVideoProcessorSetStreamPalette;

VOID APIENTRY* pfnVideoProcessorSetStreamPalette(
  _In_       D3D10DDI_HDEVICE           hDevice,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_       UINT                       StreamIndex,
  _In_       UINT                       Count,
  _In_ const UINT                       *pEntries
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSOR


### -param UINT


### -param *








#### - Count [in]

The number of elements in the array that is referenced by the <i>pEntries</i> parameter.


#### - StreamIndex [in]

The zero-based index of the input stream.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




#### - pEntries [in]

A pointer to an array of palette entries. For RGB streams, the palette entries are specified in the <b>DXGI_FORMAT_B8G8R8A8</b> format. For YCbCr streams, the palette entries are specified in the <b>DXGI_FORMAT_AYUV</b> format. 


## -returns



This callback function does not return a value.




## -remarks



The <b>VideoProcessorSetStreamPalette</b> function is called only for input streams that have a palettized color format. Palettized formats with 4 bits per pixel (bpp) use the first 16 entries in the list. Formats with 8 bpp use the first 256 entries.



If a pixel has a palette index greater than the number of entries, the device treats the pixel as white with opaque alpha. For full-range RGB, this value is (255, 255, 255, 255); for YCbCr the value is (255, 235, 128, 128).



The driver reports its ability to support palettized color formats in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability, it can be configured with color-palette entries for an input stream.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability, the Microsoft Direct3D runtime does not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode.md">VideoProcessorSetOutputStereoMode</a> function.</div>
<div> </div>
If the driver does not report the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability, every palette entry must have an alpha value of 0xFF (opaque).




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPALETTE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

