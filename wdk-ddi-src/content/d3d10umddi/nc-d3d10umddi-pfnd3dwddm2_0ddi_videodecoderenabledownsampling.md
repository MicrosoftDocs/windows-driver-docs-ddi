---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING
title: PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING (d3d10umddi.h)
description: Indicates that decoder down-sampling will be used and that the driver should allocate the appropriate reference frames. Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers.
old-location: display\videodecoderenabledownsampling.htm
ms.assetid: 0817C977-1113-4953-B60C-A69185443335
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING callback function"]
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING, PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING callback, d3d10umddi/pfnVideoDecoderEnableDownsampling, display.videodecoderenabledownsampling, pfnVideoDecoderEnableDownsampling, pfnVideoDecoderEnableDownsampling callback function [Display Devices]
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
 - "d3d10umddi/pfnVideoDecoderEnableDownsampling"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoDecoderEnableDownsampling
product:
 - Windows
---

# PFND3DWDDM2_0DDI_VIDEODECODERENABLEDOWNSAMPLING callback function

## -description

Indicates that decoder down-sampling will be used and that the driver should allocate the appropriate reference frames.  Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param hDecoder

A handle to the decoder object.

### -param InputColorSpace

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type">D3DDDI_COLOR_SPACE_TYPE</a> value that indicates the color space information of the reference frame data.

### -param pOutputDesc

Indicates the resolution and the format of the output/display frames.  This is the destination resolution and format of the down-sample operation.



<div class="alert"><b>Note</b>  The decode profile member (<b>Guid</b>) of <b>pOutputDesc</b> can be ignored.</div>
<div> </div>

### -param OutputColorSpace

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type">D3DDDI_COLOR_SPACE_TYPE</a> value that indicates the color space information of the output/display frames.

### -param ReferenceFrameCount

Indicates the number of reference frame used.

## -returns

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks

This function can only be called once, prior to the first <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a> call.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a>

