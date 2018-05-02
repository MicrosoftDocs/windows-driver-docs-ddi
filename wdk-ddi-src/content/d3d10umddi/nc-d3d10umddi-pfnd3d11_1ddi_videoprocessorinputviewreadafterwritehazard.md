---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD
title: PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD
author: windows-driver-content
description: Notifies the display miniport driver that the VideoProcessorBlt function is about to be called to read from a specified input view resource for a video processor.
old-location: display\videoprocessorinputviewreadafterwritehazard.htm
old-project: display
ms.assetid: 320cfd00-656a-47ce-912e-7196986deaae
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD, PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD callback, VideoProcessorInputViewReadAfterWriteHazard, VideoProcessorInputViewReadAfterWriteHazard callback function [Display Devices], d3d10umddi/VideoProcessorInputViewReadAfterWriteHazard, display.videoprocessorinputviewreadafterwritehazard
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
-	VideoProcessorInputViewReadAfterWriteHazard
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD callback function


## -description


Notifies the display miniport driver that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451703">VideoProcessorBlt</a> function is about to be called to read from a specified input view resource for a video processor. This resource had previously been written to by either the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451701">VideoDecoderSubmitBuffers</a> or the <a href="https://msdn.microsoft.com/36aeb826-251e-404e-8ce3-6b2246ff07bc">DecryptionBlt(D3D11_1)</a> functions.


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3








#### - hDevice [in]

A handle to the display device (graphics context).


#### - hResource [in]

A handle to the driver's private data for an input view resource object. This handle is created though a call to the <a href="https://msdn.microsoft.com/f3942c53-e366-41c5-9f43-d093fa6b6ed6">CreateVideoProcessorInputView</a> function.


#### - hView [in]

A handle to the driver's private data for the video processor input view that was created through a call to the <a href="https://msdn.microsoft.com/f3942c53-e366-41c5-9f43-d093fa6b6ed6">CreateVideoProcessorInputView</a> function.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/f3942c53-e366-41c5-9f43-d093fa6b6ed6">CreateVideoProcessorInputView</a>



<a href="https://msdn.microsoft.com/36aeb826-251e-404e-8ce3-6b2246ff07bc">DecryptionBlt(D3D11_1)</a>
 

 

