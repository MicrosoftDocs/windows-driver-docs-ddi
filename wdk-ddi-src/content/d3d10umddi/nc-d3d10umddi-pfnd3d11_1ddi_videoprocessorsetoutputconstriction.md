---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION
author: windows-driver-content
description: Sets the amount of downsampling to perform on the output.
old-location: display\videoprocessorsetoutputconstriction.htm
old-project: display
ms.assetid: 4b34a76b-2e56-4656-9112-ad2e1d53525d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoprocessorsetoutputconstriction, pfnVideoProcessorSetOutputConstriction callback function [Display Devices], pfnVideoProcessorSetOutputConstriction, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION, d3d10umddi/pfnVideoProcessorSetOutputConstriction
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
-	pfnVideoProcessorSetOutputConstriction
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION callback


## -description


Sets the amount of downsampling to perform on the output.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION pfnVideoProcessorSetOutputConstriction;

VOID APIENTRY* pfnVideoProcessorSetOutputConstriction(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_ BOOL                       Enabled,
  _In_ SIZE                       ConstrictonSize
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11_1DDI_HVIDEOPROCESSOR



### -param BOOL



### -param SIZE






#### - ConstrictonSize [in]

The sampling size.


#### - Enabled [in]

If <b>TRUE</b>, downsampling is enabled. Otherwise, downsampling is disabled and the <i>ConstrictonSize</i> member is ignored. 




#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




## -returns


This callback function does not return a value.



## -remarks


Downsampling is sometimes used to reduce the quality of premium content when other forms of content protection are not available. 

By default, downsampling is disabled.

If the <i>Enable</i> parameter is TRUE, the display miniport driver downsamples the composed image to the specified size, and then scales it back to the size of the target rectangle.



The width and height of the <i>ConstrictonSize</i> parameter must be greater than zero. If the size is larger than the target rectangle, downsampling does not occur.



The driver reports its ability to support downsampling through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION</b> capability, it supports the ability to downsample the composed image.
<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetOutputConstriction</b> function.</div><div> </div>


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCONSTRICTION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

