---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERENDFRAME
title: PFND3D11_1DDI_VIDEODECODERENDFRAME (d3d10umddi.h)
description: Completes a DirectX Video Acceleration (DXVA) decoding operation for a video frame.
old-location: display\videodecoderendframe.htm
ms.assetid: f0110435-d060-4f4b-ad29-baaeb8fc2e0e
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODERENDFRAME, PFND3D11_1DDI_VIDEODECODERENDFRAME callback, d3d10umddi/pfnVideoDecoderEndFrame, display.videodecoderendframe, pfnVideoDecoderEndFrame, pfnVideoDecoderEndFrame callback function [Display Devices]
f1_keywords:
 - "d3d10umddi/pfnVideoDecoderEndFrame"
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
- pfnVideoDecoderEndFrame
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEODECODERENDFRAME callback function


## -description


Completes a DirectX Video Acceleration (DXVA) decoding operation for a video frame.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDecoder* [in]

A handle to the video decoder object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a> function.





## -remarks



The <b>VideoDecoderEndFrame</b> completes the decoding operation that was started when the Microsoft Direct3D runtime called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a>. <b>VideoDecoderEndFrame</b> signals to the driver that all video data has been submitted for the video frame.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a>
 

 

