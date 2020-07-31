---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STREAM
title: D3D11_1DDI_VIDEO_PROCESSOR_STREAM (d3d10umddi.h)
description: Contains stream-level data for the VideoProcessorBlt function.
old-location: display\d3d11_1ddi_video_processor_stream.htm
ms.assetid: 7edbe37b-ea45-4d37-908c-25c840e4cd74
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_STREAM structure"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_STREAM, D3D11_1DDI_VIDEO_PROCESSOR_STREAM structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STREAM, display.d3d11_1ddi_video_processor_stream
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STREAM"
 - "D3D11_1DDI_VIDEO_PROCESSOR_STREAM"
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
- D3D11_1DDI_VIDEO_PROCESSOR_STREAM
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_STREAM
---

# D3D11_1DDI_VIDEO_PROCESSOR_STREAM structure


## -description


Contains stream-level data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a> function.


## -struct-fields




### -field Enable

Specifies whether this input stream is enabled. If the value is <b>TRUE</b>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a> function blits this stream to the output surface. Otherwise, this stream is not blitted.

The maximum number of streams that can be enabled at one time is given in the <b>MaxInputStreams</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure.


### -field OutputIndex

The zero-based index number of the output frame.


### -field InputFrameOrField

The zero-based index number of the input frame or field.


### -field PastFrames

The number of past reference frames.


### -field FutureFrames

The number of future reference frames.


### -field pPastSurfaces

A <b>D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW</b> pointer to an array of  pointers, allocated by the caller. This array contains the past reference frames for the video processing operation. The number of elements in the array is equal to <b>PastFrames</b>.


### -field hInputSurface

A <b>D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW</b> pointer to the surface that contains the current input frame.


### -field pFutureSurfaces

A <b>D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW</b> pointer to an array of pointers, allocated by the caller. This array contains the future reference frames for the video processing operation. The number of elements in the array is equal to <b>FutureFrames</b>.


### -field pPastSurfacesRight

If the stereo 3-D format is <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE</b>, this member is a <b>D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW</b> pointer to an array of   pointers that contains the past reference frames for the right view. The number of elements in the array is equal to <b>PastFrames</b>.

For any other stereo 3-D format, set this member to <b>NULL</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a>.






### -field hInputSurfaceRight

If the stereo 3-D format is <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE</b>, this member is a <b>D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW</b> pointer to the current input frame for the right view.

For any other stereo 3-D format, set this member to <b>NULL</b>. 

 




### -field pFutureSurfacesRight

If the stereo 3-D format is <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE</b>, this member is a <b>D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW</b> pointer to an array of  pointers that contains the future reference frames for the right view. The number of elements in the array is equal to <b>FutureFrames</b>.



For any other stereo 3-D format, set this member to <b>NULL</b>. 




## -remarks



If the stereo 3-D format is <b>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE</b>, the <b>pPastSurfaces</b>, <b>pInputSurface</b>, and <b>pFutureSurfaces</b> members contain the left view.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a>
 

 

