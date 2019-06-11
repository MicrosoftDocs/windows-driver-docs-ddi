---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY (d3d10umddi.h)
description: Sets the luma key for an input stream on the video processor.
old-location: display\videoprocessorsetstreamlumakey.htm
ms.assetid: 1b5ca40d-1836-4c80-af55-8d20c6792445
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY callback, d3d10umddi/pfnVideoProcessorSetStreamLumaKey, display.videoprocessorsetstreamlumakey, pfnVideoProcessorSetStreamLumaKey, pfnVideoProcessorSetStreamLumaKey callback function [Display Devices]
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
- pfnVideoProcessorSetStreamLumaKey
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY callback function


## -description


Sets the luma key for an input stream on the video processor.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*Lower* [in]

The lower bound for the luma key. The valid range is from zero to one. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.

</div>
<div> </div>

### -param Arg5

*Enable* [in]

If <b>TRUE</b>, the luma key is enabled on the specified input stream of the video processor.

### -param Arg6

*Upper* [in]

The upper bound for the luma key. The valid range is from zero to one. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.

</div>
<div> </div>





## -returns



This callback function does not return a value.




## -remarks



The values of <i>Lower</i> and <i>Upper</i> give the lower and upper bounds of the luma key by using a nominal range from zero to one. Given a format with <i>n</i> bits per channel, these values are converted to luma values as follows:

<code>val = f * ((1 << n)-1)</code>

Any pixel whose luma value falls within the upper and lower bounds (inclusive) is treated as transparent.

For example, if the pixel format uses 8-bit luma, the upper bound is calculated as follows:

<code>BYTE Y = BYTE(max(min(1.0, Upper), 0.0) * 255.0)</code>

Note that the value is clamped to the range from zero to one before multiplying by 255.

The driver reports its ability to support stereo alpha blending for an input stream  in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY</b> capability, it can be enabled or disabled to set a luma key on an input stream of the video processor.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetStreamLumaKey</b> function.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a>
 

 

