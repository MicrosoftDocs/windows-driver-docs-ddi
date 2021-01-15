---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERENDFRAME
title: PFND3D11_1DDI_VIDEODECODERENDFRAME (d3d10umddi.h)
description: Completes a DirectX Video Acceleration (DXVA) decoding operation for a video frame.
old-location: display\videodecoderendframe.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEODECODERENDFRAME callback function"]
ms.keywords: PFND3D11_1DDI_VIDEODECODERENDFRAME, PFND3D11_1DDI_VIDEODECODERENDFRAME callback, d3d10umddi/pfnVideoDecoderEndFrame, display.videodecoderendframe, pfnVideoDecoderEndFrame, pfnVideoDecoderEndFrame callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_VIDEODECODERENDFRAME
 - d3d10umddi/PFND3D11_1DDI_VIDEODECODERENDFRAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_VIDEODECODERENDFRAME
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

A handle to the video decoder object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a> function.

## -remarks

The <b>VideoDecoderEndFrame</b> completes the decoding operation that was started when the Microsoft Direct3D runtime called <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a>. <b>VideoDecoderEndFrame</b> signals to the driver that all video data has been submitted for the video frame.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a>

