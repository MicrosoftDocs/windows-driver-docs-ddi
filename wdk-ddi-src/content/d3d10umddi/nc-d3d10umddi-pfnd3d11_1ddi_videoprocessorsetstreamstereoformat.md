---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT (d3d10umddi.h)
description: Enables or disables stereo 3D video for an input stream on the video processor. In addition, this function specifies the layout of the video frames in memory.
old-location: display\videoprocessorsetstreamstereoformat.htm
ms.assetid: bc79f431-d23e-4440-a8c5-50c29c48444e
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT callback, d3d10umddi/pfnVideoProcessorSetStreamStereoFormat, display.videoprocessorsetstreamstereoformat, pfnVideoProcessorSetStreamStereoFormat, pfnVideoProcessorSetStreamStereoFormat callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetStreamStereoFormat"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoProcessorSetStreamStereoFormat
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMSTEREOFORMAT callback function


## -description


Enables or disables stereo 3D video for an input stream on the video processor. In addition, this function specifies the layout of the video frames in memory.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*Enable* [in]

If <b>TRUE</b>, stereo 3D is enabled for the input stream.



If <b>FALSE</b>, stereo 3D is disabled for the input stream.

The driver must ignore the remaining parameters for this function.

### -param Arg5

*StereoFormat* [in]

Specifies the layout of the two stereo views in memory, as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> value.

### -param Arg6

*LeftViewFrame0* [in]

If <b>TRUE</b>, frame 0 contains the left view. Otherwise, frame 0 contains the right view.

This parameter is ignored for the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> values:



<ul>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO 
</b>

</li>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b>

</li>
</ul>

### -param Arg7

*BaseViewFrame0* [in]

If <b>TRUE</b>, frame 0 contains the base view. Otherwise, frame 1 contains the base view.


This parameter is ignored for the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a> values:



<ul>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO 
</b>

</li>
<li>
<b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</b>

</li>
</ul>

### -param Arg8

*FlipMode* [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a> enumeration value that specifies whether one of the views is flipped.

### -param Arg9

*MonoOffset* [in]

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
	Specify both resources for the stereo input data of the base view.  When <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a> is called, the stream data is passed as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_stream">D3D11_1DDI_VIDEO_PROCESSOR_STREAM</a> structure, with the <b>hInputSurface</b> member specifying frame 0 and the <b>hInputSurfaceRight</b> specifying frame 1.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_flip_mode">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FLIP_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_format">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_stream">D3D11_1DDI_VIDEO_PROCESSOR_STREAM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>
 

 

