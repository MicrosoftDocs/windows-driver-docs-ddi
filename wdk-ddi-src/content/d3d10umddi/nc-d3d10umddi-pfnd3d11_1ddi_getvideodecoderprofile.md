---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERPROFILE
title: PFND3D11_1DDI_GETVIDEODECODERPROFILE (d3d10umddi.h)
description: Queries the attributes of a specified video decoder profile.
old-location: display\getvideodecoderprofile.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEODECODERPROFILE callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERPROFILE, PFND3D11_1DDI_GETVIDEODECODERPROFILE callback, d3d10umddi/pfnGetVideoDecoderProfile, display.getvideodecoderprofile, pfnGetVideoDecoderProfile, pfnGetVideoDecoderProfile callback function [Display Devices]
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
 - PFND3D11_1DDI_GETVIDEODECODERPROFILE
 - d3d10umddi/PFND3D11_1DDI_GETVIDEODECODERPROFILE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_GETVIDEODECODERPROFILE
---

# PFND3D11_1DDI_GETVIDEODECODERPROFILE callback function


## -description

Queries the attributes of a specified video decoder profile.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*Index* [in]

The zero-based index of the video decoder profile. The display miniport driver returns the maximum number of video decoder profiles that it supports through a call to its <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount">GetVideoDecoderProfileCount</a> function.

### -param unnamedParam3

*pDecodeDesc* [out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the attributes of the specified video decoder profile.

## -remarks

The Microsoft Direct3D runtime verifies that the <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderProfile</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofilecount">GetVideoDecoderProfileCount</a>

