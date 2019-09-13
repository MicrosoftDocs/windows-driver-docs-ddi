---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING
title: PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING (d3d10umddi.h)
description: Updates the decoder down sampling parameters. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videodecoderupdatedownsampling.htm
ms.assetid: DBF0F62D-E6E5-4711-9A7A-19C88F62575D
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING, PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING callback, d3d10umddi/pfnVideoDecoderUpdateDownsampling, display.videodecoderupdatedownsampling, pfnVideoDecoderUpdateDownsampling, pfnVideoDecoderUpdateDownsampling callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
 - "d3d10umddi/pfnVideoDecoderUpdateDownsampling"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoDecoderUpdateDownsampling
product:
 - Windows
---

# PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING callback function

## -description

Updates the decoder down sampling parameters. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param hDecoder

A handle to the video decoder object.

### -param pOutputDesc

Contains the resolution and the format of the output/display frames.  This is the destination resolution and format of the down sample operation.



<div class="alert"><b>Note</b>  The decode profile member (<b>Guid</b>) of <b>pOutputDesc</b> can be ignored.</div>
<div> </div>

### -param OutputColorSpace

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type">D3DDDI_COLOR_SPACE_TYPE</a> value that contains the color space information of the output/display frame data.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks

This function can only be called after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling">VideoDecoderEnableDownsampling</a> has been called.



This function will only be called if the driver reports the <b>D3DWDDM2_0DDI_VIDEO_DECODER_CAPS_DOWN_SAMPLE_DYNAMIC</b> capability.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling">VideoDecoderEnableDownsampling</a>

