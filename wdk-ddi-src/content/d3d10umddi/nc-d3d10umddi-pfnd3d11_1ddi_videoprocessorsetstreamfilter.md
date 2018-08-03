---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
author: windows-driver-content
description: Enables or disables an image filter for an input stream on the video processor.
old-location: display\videoprocessorsetstreamfilter.htm
tech.root: display
ms.assetid: e44e5e4a-20e1-4327-b64c-5806d1bb2ece
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER callback, d3d10umddi/pfnVideoProcessorSetStreamFilter, display.videoprocessorsetstreamfilter, pfnVideoProcessorSetStreamFilter, pfnVideoProcessorSetStreamFilter callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoProcessorSetStreamFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER callback function


## -description


Enables or disables an image filter for an input stream on the video processor.




## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param Arg4


### -param Arg5


### -param Arg6








#### - Enable [in]

If <b>TRUE</b>, the filter is enabled on the video processor.


#### - Filter [in]

The filter, specified as a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450982">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a> value.




#### - Level [in]

The filter level. The meaning of this value is defined by the independent hardware vendor (IHV).

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.

</div>
<div> </div>

#### - StreamIndex [in]

The zero-based index of the input stream.


#### - hDevice [in]

A handle to the display device (graphics context).




#### - hVideoProcessor [in]

A handle to the video processor object that was created through a call to the <a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a> function. 




## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450982">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a>
 

 

