---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE
author: windows-driver-content
description: Specifies whether the video processor produces stereo video frames.
old-location: display\videoprocessorsetoutputstereomode.htm
old-project: display
ms.assetid: 3e3eaaa6-2725-49de-bca6-df2da1b4324b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoprocessorsetoutputstereomode, pfnVideoProcessorSetOutputStereoMode callback function [Display Devices], pfnVideoProcessorSetOutputStereoMode, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE, d3d10umddi/pfnVideoProcessorSetOutputStereoMode
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	D3d10umddi.h
apiname: 
-	pfnVideoProcessorSetOutputStereoMode
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE callback


## -description


Specifies whether the video processor produces stereo video frames.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE pfnVideoProcessorSetOutputStereoMode;

VOID APIENTRY* pfnVideoProcessorSetOutputStereoMode(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_ BOOL                       Enable
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11_1DDI_HVIDEOPROCESSOR



### -param BOOL






#### - Enable [in]

If <b>TRUE</b>, stereo output is enabled. Otherwise, the video processor produces mono video frames.




#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




## -returns


This callback function does not return a value.



## -remarks


By default, the video processor produces mono video frames. If stereo video is enabled, the stereo output format is set through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a> function.



The driver reports its ability to support stereo video modes through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, it can be enabled or disabled to produce stereo video frames.
<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetOutputStereoMode</b> function.</div><div> </div>


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

