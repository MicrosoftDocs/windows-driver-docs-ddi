---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORBLT
title: PFND3D11_1DDI_VIDEOPROCESSORBLT
author: windows-driver-content
description: Performs a video processing operation on one or more input samples and writes the result to a Direct3D surface.
old-location: display\videoprocessorblt.htm
old-project: display
ms.assetid: 7a3e17cb-0397-4051-8443-fb2edf3b4cff
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoprocessorblt, pfnVideoProcessorBlt callback function [Display Devices], pfnVideoProcessorBlt, PFND3D11_1DDI_VIDEOPROCESSORBLT, PFND3D11_1DDI_VIDEOPROCESSORBLT, d3d10umddi/pfnVideoProcessorBlt
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
-	pfnVideoProcessorBlt
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_VIDEOPROCESSORBLT callback


## -description


Performs a video processing operation on one or more input samples and writes the result to a Direct3D surface.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORBLT pfnVideoProcessorBlt;

HRESULT APIENTRY* pfnVideoProcessorBlt(
  _In_       D3D10DDI_HDEVICE                     hDevice,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR           hVideoProcessor,
  _In_       D3D11_1DDI_HVIDEOPROCESSOROUTPUTVIEW hOutputView,
  _In_       UINT                                 OutputFrame,
  _In_       UINT                                 StreamCount,
  _In_ const D3D11_1DDI_VIDEO_PROCESSOR_STREAM    *pStream
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSOR


### -param D3D11_1DDI_HVIDEOPROCESSOROUTPUTVIEW


### -param UINT


### -param *








#### - OutputFrame [in]

The zero-based index of the output video frame.


#### - StreamCount [in]

The number of input streams to process in the array referenced by the <i>pStream</i> parameter.



<div class="alert"><b>Note</b>  The maximum value of this parameter is specified by the <b>MaxStreamStates</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. The maximum number of streams that can be enabled at one time is given in the <b>MaxInputStreams</b> member of that structure.

</div>
<div> </div>

#### - hDevice [in]

A handle to the display device (graphics context).




#### - hOutputView [in]

A handle to the resource for the output view of the video processor. This handle was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessorOutputView</a> function.




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function.




#### - pStream [in]

A pointer to an array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_stream.md">D3D11_1DDI_VIDEO_PROCESSOR_STREAM</a> structures that contain information about the input streams.


## -returns



<b>VideoProcessorBlt</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The video processing operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The <b>VideoProcessorBlt</b> performs all of the video processing based on the stream states and bit-block transfer (bitblt) states that have been previously set.

The Microsoft Direct3D runtime performs the following data validation before it calls the driver's <b>VideoProcessorBlt</b> function:

<ul>
<li>
The input and output <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures may be adjusted if the rectangles are not aligned properly according to the requirements of the format.


</li>
<li>
If the video processor has been enabled to produce stereo samples, the output view must contain a texture array of two elements.
Also, at least one stereo stream must be specified.

If the video processor has been disabled from producing stereo samples, the output view must contain a single element.
 Also, the stereo format cannot be configured as <b>D3D11_VIDEO_PROCESSOR_STEREO_FORMAT_MONO</b>.


<div class="alert"><b>Note</b>  A video processor is enabled or disabled for the production of stereo samples through a call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode.md">VideoProcessorSetOutputStereoMode</a>.</div>
<div> </div>
</li>
<li>
Each input stream is specified through a 	<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_stream.md">D3D11_1DDI_VIDEO_PROCESSOR_STREAM</a> structure. If the stereo format of the input stream is configured to be <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE</b>, the <b>pInputSurfaceRight</b> member must not be set to NULL.  Otherwise, the <b>pInputSurfaceRight</b> must be set to NULL.



<div class="alert"><b>Note</b>  The stereo format for an input stream is configured through a call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a>.</div>
<div> </div>
</li>
</ul>
If multiple input streams are enabled and the video processor is enabled to produce stereo output, it is possible that one of the input streams may be a mono sample.



<div class="alert"><b>Note</b>  This function does not honor a D3D11 predicate that may have been set.</div>
<div> </div>



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_stream.md">D3D11_1DDI_VIDEO_PROCESSOR_STREAM</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputstereomode.md">VideoProcessorSetOutputStereoMode</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<b>CreateVideoProcessorOutputView</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORBLT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

