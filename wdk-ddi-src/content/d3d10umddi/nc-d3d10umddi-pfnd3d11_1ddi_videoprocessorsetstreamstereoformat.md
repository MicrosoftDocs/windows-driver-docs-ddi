---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT
author: windows-driver-content
description: Enables or disables stereo 3D video for an input stream on the video processor. In addition, this function specifies the layout of the video frames in memory.
old-location: display\videoprocessorsetstreamstereoformat.htm
old-project: display
ms.assetid: bc79f431-d23e-4440-a8c5-50c29c48444e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.videoprocessorsetstreamstereoformat, pfnVideoProcessorSetStreamStereoFormat callback function [Display Devices], pfnVideoProcessorSetStreamStereoFormat, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT, d3d10umddi/pfnVideoProcessorSetStreamStereoFormat
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
-	pfnVideoProcessorSetStreamStereoFormat
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT callback


## -description


Enables or disables stereo 3D video for an input stream on the video processor. In addition, this function specifies the layout of the video frames in memory.




## -prototype


````
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT pfnVideoProcessorSetStreamStereoFormat;

VOID APIENTRY* pfnVideoProcessorSetStreamStereoFormat(
  _In_ D3D10DDI_HDEVICE                            hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR                  hVideoProcessor,
  _In_ UINT                                        StreamIndex,
  _In_ BOOL                                        Enable,
  _In_ D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT    StereoFormat,
  _In_ BOOL                                        LeftViewFrame0,
  _In_ BOOL                                        BaseViewFrame0,
  _In_ D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE FlipMode,
  _In_ int                                         MonoOffset
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEOPROCESSOR


### -param UINT


### -param BOOL


### -param D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT


### -param D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE


### -param int








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




#### - StreamIndex [in]

The zero-based index of the input stream.


#### - Enable [in]

If <b>TRUE</b>, stereo 3D is enabled for the input stream.



If <b>FALSE</b>, stereo 3D is disabled for the input stream.

 The driver must ignore the remaining parameters for this function.


#### - StereoFormat [in]

Specifies the layout of the two stereo views in memory, as a <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> value.




#### - LeftViewFrame0 [in]

If <b>TRUE</b>, frame 0 contains the left view. Otherwise, frame 0 contains the right view.

This parameter is ignored for the following <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> values:



<ul>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO 
</b>

</li>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b>

</li>
</ul>

#### - BaseViewFrame0 [in]

If <b>TRUE</b>, frame 0 contains the base view. Otherwise, frame 1 contains the base view.


This parameter is ignored for the following <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> values:



<ul>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO 
</b>

</li>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b>

</li>
</ul>

#### - FlipMode [in]

A <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a> enumeration value that specifies whether one of the views is flipped.




#### - MonoOffset [in]

If the <i>StereoFormat</i> parameter is set to <b>D3D11_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b>, this parameter specifies how to generate the left and right views. For more information, see the Remarks section.

<div class="alert"><b>Note</b>  If the <i>StereoFormat</i> parameter is not set to <b>D3D11_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b>, this parameter must be set to zero and ignored by the driver.</div>
<div> </div>

## -returns



This callback function does not return a value.




## -remarks



For stereo formats of  <b>D3D11_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b>, the driver processes the <i>MonoOffset</i> parameter in the following way:

<ul>
<li>
If the parameter is positive, the right view is shifted to the right by that many pixels, and the left view is shifted to the left by the same amount. 


</li>
<li>
If the parameter is negative, the right view is shifted to the left by that many pixels, and the left view is shifted to the right by the same amount. 


</li>
</ul>
For stereo formats of <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE</b>, the application can set the <i>BaseViewFrame0</i> parameter to convert stereo data to mono. The application does this in one of the following ways:

<ul>
<li>

Specifies a single resource for the mono input data of the base view.

</li>
<li>
	Specify both resources for the stereo input data of the base view.  When <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a> is called, the stream data is passed as a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_stream.md">D3D11_1DDI_VIDEO_PROCESSOR_STREAM</a> structure, with the <b>hInputSurface</b> member specifying frame 0 and the <b>hInputSurfaceRight</b> specifying frame 1.

</li>
</ul>



## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format.md">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_stream.md">D3D11_1DDI_VIDEO_PROCESSOR_STREAM</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

