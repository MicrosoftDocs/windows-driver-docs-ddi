---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
author: windows-driver-content
description: Sets the rate at which the video processor produces output frames for an input stream.
old-location: display\videoprocessorsetstreamoutputrate.htm
old-project: display
ms.assetid: fc1236f2-fcbf-4b3f-978f-a34260b78159
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoprocessorsetstreamoutputrate, pfnVideoProcessorSetStreamOutputRate callback function [Display Devices], pfnVideoProcessorSetStreamOutputRate, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE, d3d10umddi/pfnVideoProcessorSetStreamOutputRate
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
-	pfnVideoProcessorSetStreamOutputRate
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback


## -description


Sets the rate at which the video processor produces output frames for an input stream.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE pfnVideoProcessorSetStreamOutputRate;

VOID APIENTRY* pfnVideoProcessorSetStreamOutputRate(
  _In_       D3D10DDI_HDEVICE                       hDevice,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR             hVideoProcessor,
  _In_       UINT                                   StreamIndex,
  _In_       D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE OutputRate,
  _In_       BOOL                                   RepeatFrame,
  _In_ const DXGI_RATIONAL                          *pCustomRate
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param D3D11_1DDI_HVIDEOPROCESSOR



### -param UINT



### -param D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE



### -param BOOL



### -param *






#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




#### - StreamIndex [in]

The zero-based index of the input stream.


#### - OutputRate [in]

The output rate, specified as a <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate.md">D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE</a> value.

For more information, see the Remarks section.


#### - RepeatFrame [in]

Specifies how the driver performs frame-rate conversion, if it is required.



If the <i>RepeatFrame</i> parameter is <b>TRUE</b>,  the driver should repeat frames. 



If the <i>RepeatFrame</i> parameter is <b>FALSE</b>,  the driver should interpolate frames.
<div class="alert"><b>Note</b>  If the <b>VideoProcessorSetStreamOutputRate</b> function is never called, the driver should interpolate frames by default.</div><div> </div>

#### - pCustomRate [in]

A pointer to a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure. If the <i>OutputRate</i> parameter is set to <b>D3D11_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM</b>, this parameter specifies the exact output rate. Otherwise, this parameter is ignored and can be set to NULL.




## -returns


This callback function does not return a value.



## -remarks


The standard output rates that are defined by  <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate.md">D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE</a> enumeration values are normal frame-rate (<b>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_NORMAL</b>) and half frame-rate (<b>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_HALF</b>). 

If the driver supports custom rates for rate conversion or inverse telecine, it can use a custom rate if the <i>OutputRate</i> parameter is set to <b>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM</b>. The custom rate is specified by the <i>pCustomRate</i> parameter.
<div class="alert"><b>Note</b>  The driver reports its custom rates  in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md">GetVideoProcessorCustomRate</a> function.

</div><div> </div>Depending on the output rate, the driver might have to convert the frame rate. If so, the value of the <i>RepeatFrame</i> parameter controls whether the driver creates interpolated frames or repeats input frames.





## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md">GetVideoProcessorCustomRate</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate.md">D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

