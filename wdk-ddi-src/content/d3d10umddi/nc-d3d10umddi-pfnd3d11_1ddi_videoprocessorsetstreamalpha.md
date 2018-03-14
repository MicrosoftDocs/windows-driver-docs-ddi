---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA
author: windows-driver-content
description: Sets the planar alpha for an input stream on the video processor.
old-location: display\videoprocessorsetstreamalpha.htm
old-project: display
ms.assetid: 9208bcd7-c030-4c2f-b3bc-e1bff3839cef
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA, d3d10umddi/pfnVideoProcessorSetStreamAlpha, display.videoprocessorsetstreamalpha, pfnVideoProcessorSetStreamAlpha, pfnVideoProcessorSetStreamAlpha callback function [Display Devices]
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
-	pfnVideoProcessorSetStreamAlpha
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA callback


## -description


Sets the planar alpha for an input stream on the video processor.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA pfnVideoProcessorSetStreamAlpha;

VOID APIENTRY* pfnVideoProcessorSetStreamAlpha(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_ UINT                       StreamIndex,
  _In_ BOOL                       Enable,
  _In_ FLOAT                      Alpha
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSOR


### -param UINT


### -param BOOL


### -param FLOAT








#### - Alpha [in]

A pointer to a <b>FLOAT</b> value that specifies the planar alpha value. The value can range from 0.0 (transparent) to 1.0 (opaque). 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is <b>FALSE</b>, this parameter is ignored.

</div>
<div> </div>

#### - Enable [in]

If <b>TRUE</b>, alpha blending is to be enabled on the video processor.


#### - StreamIndex [in]

The zero-based index of the input stream.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




## -returns



This callback function does not return a value.




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
<div class="alert"><b>Note</b>  Palette-entry alpha values apply only to palettized color formats, and only when the device advertises support for the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. Otherwise, this factor equals 1.0.</div>
<div> </div>
The destination alpha value is computed according to the alpha fill mode. For more information, see <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a>


The driver reports its ability to support stereo alpha blending for an input stream in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM </b> capability, it can be enabled or disabled to produce stereo video frames.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetStreamAlpha</b> function.</div>
<div> </div>



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

