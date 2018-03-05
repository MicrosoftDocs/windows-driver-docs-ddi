---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE
author: windows-driver-content
description: Sets the alpha fill mode for data that the video processor writes to the render target.
old-location: display\videoprocessorsetoutputalphafillmode.htm
old-project: display
ms.assetid: 0c2cbb8f-d031-4267-b32f-620ed1ad065c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE, d3d10umddi/pfnVideoProcessorSetOutputAlphaFillMode, display.videoprocessorsetoutputalphafillmode, pfnVideoProcessorSetOutputAlphaFillMode, pfnVideoProcessorSetOutputAlphaFillMode callback function [Display Devices]
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
-	pfnVideoProcessorSetOutputAlphaFillMode
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE callback


## -description


Sets the alpha fill mode for data that the video processor writes to the render target.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE pfnVideoProcessorSetOutputAlphaFillMode;

VOID APIENTRY* pfnVideoProcessorSetOutputAlphaFillMode(
  _In_ D3D10DDI_HDEVICE                           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR                 hVideoProcessor,
  _In_ D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE FillMode,
  _In_ UINT                                       StreamIndex
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSOR


### -param D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE


### -param UINT








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




#### - FillMode [in]

The alpha fill mode, specified as a <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_alpha_fill_mode.md">D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE</a> value. For more information, see the Remarks section.


#### - StreamIndex [in]

The zero-based index of an input stream. This parameter is used if the <i>AlphaFillMode</i> parameter is set to <b>D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE_SOURCE_STREAM</b>. Otherwise, the parameter is ignored.




## -returns



This callback function does not return a value.




## -remarks



The driver reports its ability to support alpha fill modes in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL</b> capability, it supports all of the alpha fill modes that are defined by the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_alpha_fill_mode.md">D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE</a> enumeration. Otherwise, the <i>FillMode</i> parameter must be set to <b>D3D11_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE</b>. 



<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetOutputAlphaFillMode</b> function.</div>
<div> </div>
The default fill mode is <b>D3D11_VIDEO_PROCESSOR_ALPHA_FILL_MODE_OPAQUE</b>.






## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md">CreateVideoProcessorInputView</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_alpha_fill_mode.md">D3D11_1DDI_VIDEO_PROCESSOR_ALPHA_FILL_MODE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTALPHAFILLMODE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

