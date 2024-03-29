---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODEREXTENSION
title: PFND3D11_1DDI_VIDEODECODEREXTENSION (d3d10umddi.h)
description: Performs an extended function for DirectX Video Acceleration (DXVA) decoding. This method enables extensions to the basic DXVA decoder functionality.
old-location: display\videodecoderextension.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEODECODEREXTENSION callback function"]
ms.keywords: PFND3D11_1DDI_VIDEODECODEREXTENSION, PFND3D11_1DDI_VIDEODECODEREXTENSION callback, d3d10umddi/pfnVideoDecoderExtension, display.videodecoderextension, pfnVideoDecoderExtension, pfnVideoDecoderExtension callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEODECODEREXTENSION
 - d3d10umddi/PFND3D11_1DDI_VIDEODECODEREXTENSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_VIDEODECODEREXTENSION
---

# PFND3D11_1DDI_VIDEODECODEREXTENSION callback function


## -description

Performs an extended function for DirectX Video Acceleration (DXVA) decoding. This method enables extensions to the basic DXVA decoder functionality.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hDecoder* [in]

A handle to the video decoder object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a> function.

### -param unnamedParam3

*pExtension* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_videodecoderextension">D3D11_1DDIARG_VIDEODECODEREXTENSION</a> structure that contains data for the extended function.

## -returns

<b>VideoDecoderExtension</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The extension was performed successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder">CreateVideoDecoder</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_videodecoderextension">D3D11_1DDIARG_VIDEODECODEREXTENSION</a>

