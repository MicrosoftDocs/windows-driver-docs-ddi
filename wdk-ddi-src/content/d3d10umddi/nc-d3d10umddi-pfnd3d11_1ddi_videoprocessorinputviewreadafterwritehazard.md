---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD
title: PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD (d3d10umddi.h)
description: Notifies the display miniport driver that the VideoProcessorBlt function is about to be called to read from a specified input view resource for a video processor.
old-location: display\videoprocessorinputviewreadafterwritehazard.htm
ms.assetid: 320cfd00-656a-47ce-912e-7196986deaae
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD, PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD callback, VideoProcessorInputViewReadAfterWriteHazard, VideoProcessorInputViewReadAfterWriteHazard callback function [Display Devices], d3d10umddi/VideoProcessorInputViewReadAfterWriteHazard, display.videoprocessorinputviewreadafterwritehazard
ms.topic: callback
f1_keywords:
 - "d3d10umddi/VideoProcessorInputViewReadAfterWriteHazard"
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
- VideoProcessorInputViewReadAfterWriteHazard
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEOPROCESSORINPUTVIEWREADAFTERWRITEHAZARD callback function


## -description


Notifies the display miniport driver that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a> function is about to be called to read from a specified input view resource for a video processor. This resource had previously been written to by either the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecodersubmitbuffers">VideoDecoderSubmitBuffers</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt">DecryptionBlt(D3D11_1)</a> functions.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hView* [in]

A handle to the driver's private data for the video processor input view that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview">CreateVideoProcessorInputView</a> function.

### -param Arg3

*hResource* [in]

A handle to the driver's private data for an input view resource object. This handle is created though a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview">CreateVideoProcessorInputView</a> function.



## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview">CreateVideoProcessorInputView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_decryptionblt">DecryptionBlt(D3D11_1)</a>
 

 

