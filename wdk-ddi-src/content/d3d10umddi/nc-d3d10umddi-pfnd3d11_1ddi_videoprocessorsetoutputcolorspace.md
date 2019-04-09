---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE (d3d10umddi.h)
description: Sets the output color space for the video processor.
old-location: display\videoprocessorsetoutputcolorspace.htm
ms.assetid: a6d1020d-e8e1-465f-a133-59afdfe1cfce
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE callback, d3d10umddi/pfnVideoProcessorSetOutputColorSpace, display.videoprocessorsetoutputcolorspace, pfnVideoProcessorSetOutputColorSpace, pfnVideoProcessorSetOutputColorSpace callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnVideoProcessorSetOutputColorSpace
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE callback function


## -description


Sets the output color space for the video processor.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function.

### -param *

pColorspace [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450970">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a> structure that specifies the color space.


## -returns



This callback function does not return a value.




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh450970">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a> structure includes the following members:

<ul>
<li>
The <b>Usage</b> member specifies whether the output is intended for playback or video processing, such as editing or authoring. The driver can optimize the video processing based on the specified usage. 

</li>
<li>
The <b>RGB_Range</b> member specifies the RGB color range. If this member is set to zero, the transfer matrix is based on the . If this member is set to one, the RGB range is limited to index values from 16 to 235.

</li>
<li>
The <b>YCbCr_Matrix </b> member specifies the YCbCr transfer matrix. If this member is set to zero, the transfer matrix is based on the BT.601 format. If this member is set to one, the transfer matrix is based on the BT.709 format.

<div class="alert"><b>Note</b>  Both of these transfer matrixes define the black point as index 16 and the white point as index 235.</div>
<div> </div>
</li>
<li>
The <b>YCbCr_xvYCC </b> member specifies whether the output uses the conventional YCbCr format or the extended YCbCr (xvYCC) format. 

If this member is set to zero, the format that is used is the conventional YCbCr format. 

If this member is set to one, the format that is used is the extended xvYCC format.

<div class="alert"><b>Note</b>  The xvYCC format can be used with either YCbCr transfer matrix and also defines the black point as index 16 and the white point as index 235. However, the xvYCC format supports blacker luminance values in the range from 1 to 15. The xvYCC format also supports whiter luminance values in the range from 236 to 254.  Therefore, the graphics adapter must not adjust these luminance values to the standard 16 and 235 index values for the white and black point respectively.</div>
<div> </div>
</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450970">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a>
 

 

