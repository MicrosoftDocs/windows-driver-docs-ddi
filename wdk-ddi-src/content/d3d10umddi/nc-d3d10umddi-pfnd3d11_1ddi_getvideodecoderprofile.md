---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERPROFILE
title: PFND3D11_1DDI_GETVIDEODECODERPROFILE (d3d10umddi.h)
description: Queries the attributes of a specified video decoder profile.
old-location: display\getvideodecoderprofile.htm
ms.assetid: 75576152-0afd-4602-b481-bf1d6d9348b3
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERPROFILE, PFND3D11_1DDI_GETVIDEODECODERPROFILE callback, d3d10umddi/pfnGetVideoDecoderProfile, display.getvideodecoderprofile, pfnGetVideoDecoderProfile, pfnGetVideoDecoderProfile callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/pfnGetVideoDecoderProfile"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnGetVideoDecoderProfile
product:
 - Windows
---

# PFND3D11_1DDI_GETVIDEODECODERPROFILE callback function

## -description

Queries the attributes of a specified video decoder profile.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*Index* [in]

The zero-based index of the video decoder profile. The display miniport driver returns the maximum number of video decoder profiles that it supports through a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount">GetVideoDecoderProfileCount</a> function.

### -param Arg3

*pDecodeDesc* [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the attributes of the specified video decoder profile.

## -remarks

The Microsoft Direct3D runtime verifies that the <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderProfile</b> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount">GetVideoDecoderProfileCount</a>

