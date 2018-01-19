---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE
author: windows-driver-content
description: Sets the output color space for the video processor.
old-location: display\videoprocessorsetoutputcolorspace.htm
old-project: display
ms.assetid: a6d1020d-e8e1-465f-a133-59afdfe1cfce
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: pfnVideoProcessorSetOutputColorSpace
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE callback



## -description
Sets the output color space for the video processor.



## -prototype

````
PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE pfnVideoProcessorSetOutputColorSpace;

VOID APIENTRY* pfnVideoProcessorSetOutputColorSpace(
  _In_       D3D10DDI_HDEVICE                       hDevice,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR             hVideoProcessor,
  _In_ const D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE *pColorspace
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a> function. 




### -param pColorspace [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_color_space.md">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a> structure that specifies the color space.


## -returns
This callback function does not return a value.


## -remarks
The <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_color_space.md">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a> structure includes the following members:

The <b>Usage</b> member specifies whether the output is intended for playback or video processing, such as editing or authoring. The driver can optimize the video processing based on the specified usage. 

The <b>RGB_Range</b> member specifies the RGB color range. If this member is set to zero, the transfer matrix is based on the . If this member is set to one, the RGB range is limited to index values from 16 to 235.

The <b>YCbCr_Matrix </b> member specifies the YCbCr transfer matrix. If this member is set to zero, the transfer matrix is based on the BT.601 format. If this member is set to one, the transfer matrix is based on the BT.709 format.

The <b>YCbCr_xvYCC </b> member specifies whether the output uses the conventional YCbCr format or the extended YCbCr (xvYCC) format. 

If this member is set to zero, the format that is used is the conventional YCbCr format. 

If this member is set to one, the format that is used is the extended xvYCC format.


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_color_space.md">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

