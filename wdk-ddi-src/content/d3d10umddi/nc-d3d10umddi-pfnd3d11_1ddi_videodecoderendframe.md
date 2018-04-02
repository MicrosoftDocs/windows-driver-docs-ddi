---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERENDFRAME
title: PFND3D11_1DDI_VIDEODECODERENDFRAME
author: windows-driver-content
description: Completes a DirectX Video Acceleration (DXVA) decoding operation for a video frame.
old-location: display\videodecoderendframe.htm
old-project: display
ms.assetid: f0110435-d060-4f4b-ad29-baaeb8fc2e0e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODERENDFRAME, d3d10umddi/pfnVideoDecoderEndFrame, display.videodecoderendframe, pfnVideoDecoderEndFrame, pfnVideoDecoderEndFrame callback function [Display Devices]
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
-	pfnVideoDecoderEndFrame
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_VIDEODECODERENDFRAME callback


## -description


Completes a DirectX Video Acceleration (DXVA) decoding operation for a video frame.




## -parameters




### -param Arg1


### -param Arg2








#### - hDecoder [in]

A handle to the video decoder object that was created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.




#### - hDevice [in]

A handle to the display device (graphics context).




## -returns



This callback function does not return a value.




## -remarks



The <b>VideoDecoderEndFrame</b> completes the decoding operation that was started when the Microsoft Direct3D runtime called <a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>. <b>VideoDecoderEndFrame</b> signals to the driver that all video data has been submitted for the video frame.




## -see-also




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>
 

 

