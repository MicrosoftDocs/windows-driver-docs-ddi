---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
title: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT (d3d10umddi.h)
description: Specifies the layout in memory of a stereo 3-D video frame.
old-location: display\d3d11_1ddi_video_processor_stereo_format.htm
ms.assetid: 348d17f3-a688-4f63-87aa-a8588f069c5c
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT enumeration"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL, display.d3d11_1ddi_video_processor_stereo_format
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
---

# D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT enumeration


## -description


Specifies the layout in memory of a stereo 3-D video frame.


## -enum-fields




### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO

The sample does not contain stereo data. If the stereo format is not specified, this value is the default.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL

Frame 0 and frame 1 are packed side-by-side, as shown in the following diagram.

<img alt="Side-by-side packing" src="images/dxgistereo3d02.png"/>

All drivers that support stereo video must support this format.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL

Frame 0 and frame 1 are packed top-to-bottom, as shown in the following diagram.

<img alt="Top-to-bottom packing" src="images/dxgistereo3d01.png"/>

All drivers that support stereo video must support this format.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE

Frame 0 and frame 1 are placed in separate resources or in separate texture array elements within the same resource.

All drivers that support stereo video must support this format.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET

The sample contains non-stereo data. However, the driver should create a left/right output of this sample using a specified offset.  The offset is specified in the <i>MonoOffset</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a> function. 

This format is primarily intended for subtitles and other subpicture data, where the entire sample is presented on the same plane.

Support for this stereo format is optional.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED

Frame 0 and frame 1 are packed into interleaved rows, as shown in the following diagram.

<img alt="Interleaved rows" src="images/dxgistereo3d03.png"/>

Support for this stereo format is optional.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED

Frame 0 and frame 1 are packed into interleaved columns, as shown in the following diagram.

<img alt="Interleaved columns" src="images/dxgistereo3d04.png"/>

Support for this stereo format is optional.


### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD

Frame 0 and frame 1 are packed in a checkerboard format, as shown in the following diagram.

<img alt="Checkerboard packing" src="images/dxgistereo3d05.png"/>

Support for this stereo format is optional.


## -remarks



This enumeration designates the two stereo views as "frame 0" and "frame 1". The <i>LeftViewFrame0</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a> method specifies which view is the left view, and which is the right view.

For packed formats, if the source rectangle clips part of the surface, the driver interprets the rectangle in logical coordinates relative to the stereo view,  rather than absolute pixel coordinates. The result is that frame 0 and frame 1 are clipped proportionately.

To query whether the device supports stereo 3-D video, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> and check for the <b>D3D11_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> flag in the <b>FeatureCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. If this capability flag is present, it means that the driver supports all of the stereo formats that are not  listed as optional. To find out which optional formats are supported, call <b>GetVideoProcessorCaps</b> and check the <b>StereoCaps</b> member of the structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a>
 

 

