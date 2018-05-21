---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT
author: windows-driver-content
description: Specifies whether an input stream on the video processor contains interlaced or progressive frames.
old-location: display\videoprocessorsetstreamframeformat.htm
old-project: display
ms.assetid: 49310ddf-403a-4fb4-98bb-9ef00ef28310
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT callback, d3d10umddi/pfnVideoProcessorSetStreamFrameFormat, display.videoprocessorsetstreamframeformat, pfnVideoProcessorSetStreamFrameFormat, pfnVideoProcessorSetStreamFrameFormat callback function [Display Devices]
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
-	pfnVideoProcessorSetStreamFrameFormat
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT callback function


## -description


Specifies whether an input stream on the video processor contains interlaced or progressive frames.




## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param Arg4








#### - Format [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh450954">D3D11_1DDI_VIDEO_FRAME_FORMAT</a> value that specifies the frame format.




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



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450954">D3D11_1DDI_VIDEO_FRAME_FORMAT</a>
 

 

