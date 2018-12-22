---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO
description: Sets the pixel aspect ratio for an input stream on the video processor.
old-location: display\videoprocessorsetstreampixelaspectratio.htm
ms.assetid: fe472b54-09f5-4689-a3d1-0985dafa7d4b
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO callback, d3d10umddi/pfnVideoProcessorSetStreamPixelAspectRatio, display.videoprocessorsetstreampixelaspectratio, pfnVideoProcessorSetStreamPixelAspectRatio, pfnVideoProcessorSetStreamPixelAspectRatio callback function [Display Devices]
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoProcessorSetStreamPixelAspectRatio
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMPIXELASPECTRATIO callback function


## -description


Sets the pixel aspect ratio for an input stream on the video processor.




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

*Enable* [in]

If <b>TRUE</b>, the <i>pSourceRatio</i> and <i>pDestinationRatio</i> parameters contain valid values. Otherwise, the pixel aspect ratios are unspecified.

### -param *

*pSourceRatio* [in]

A pointer to a <b>DXGI_RATIONAL</b> structure that contains the pixel aspect ratio of the source rectangle. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter can be NULL.

</div>
<div> </div>

### -param *

*pDestRatio* [in]

A pointer to a <b>DXGI_RATIONAL</b> structure that contains the pixel aspect ratio of the destination rectangle. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter can be NULL.

</div>
<div> </div>



## -returns



This callback function does not return a value.




## -remarks



Pixel aspect ratios of the form 0/<i>n</i> and <i>n</i>/0 are not valid.



The default pixel aspect ratio is 1:1 (square pixels).



The driver reports its ability to support the pixel aspect ratio capability in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO </b> capability, the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439792">VideoProcessorSetStreamAlpha</a> can be called to set the pixel aspect ratios for an input stream of the video processor.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO </b> capability, the Microsoft Direct3D runtime does not call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439792">VideoProcessorSetStreamAlpha</a> function.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a>
 

 

