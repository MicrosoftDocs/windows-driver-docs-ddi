---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERGETHANDLE
title: PFND3D11_1DDI_VIDEODECODERGETHANDLE (d3d10umddi.h)
description: Returns the driver's handle for a video decoder that can be used by the application to configure content protection.
old-location: display\videodecodergethandle.htm
ms.assetid: 05c16416-d48c-44ce-b025-d62d763682bc
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODERGETHANDLE, PFND3D11_1DDI_VIDEODECODERGETHANDLE callback, d3d10umddi/pfnVideoDecoderGetHandle, display.videodecodergethandle, pfnVideoDecoderGetHandle, pfnVideoDecoderGetHandle callback function [Display Devices]
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
 - "d3d10umddi/pfnVideoDecoderGetHandle"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoDecoderGetHandle
product:
 - Windows
---

# PFND3D11_1DDI_VIDEODECODERGETHANDLE callback function

## -description

Returns the driver's handle for a video decoder that can be used by the application  to configure content protection.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

hDecoder [in]

A handle to the video decoder object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a> function.

### -param pContentProtectionHandle

A pointer to the handle.

## -returns

<b>VideoDecoderGetHandle</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The handle was returned successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

The <b>VideoDecoderGetHandle</b> function returns a driver handle for the video decoder. This handle can be used by the application to associate the decoder with a cryptographic session over the authenticated channel.

This function allows the driver to define its own handle to its state data for the video decoder. This bypasses any handle mapping that may be performed by the Microsoft Direct3D runtime.

<div class="alert"><b>Note</b>  Drivers can return the same handle in the <i>pHandle</i> parameter that was passed  in the <i>hDecoder</i> parameter.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_videodecoderextension">D3D11_1DDIARG_VIDEODECODEREXTENSION</a>

