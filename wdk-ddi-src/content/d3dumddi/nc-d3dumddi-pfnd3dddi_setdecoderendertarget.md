---
UID: NC:d3dumddi.PFND3DDDI_SETDECODERENDERTARGET
title: PFND3DDDI_SETDECODERENDERTARGET (d3dumddi.h)
description: The SetDecodeRenderTarget function sets the render target surface for decoding operations.
old-location: display\setdecoderendertarget.htm
tech.root: display
ms.assetid: d522b0f3-ca9c-4e79-96ad-ea9477858ef4
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETDECODERENDERTARGET callback function"]
ms.keywords: PFND3DDDI_SETDECODERENDERTARGET, PFND3DDDI_SETDECODERENDERTARGET callback, SetDecodeRenderTarget, SetDecodeRenderTarget callback function [Display Devices], UserModeDisplayDriver_Functions_e5c55218-5663-4689-a696-6b9b1c0a7cce.xml, d3dumddi/SetDecodeRenderTarget, display.setdecoderendertarget
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
req.typenames: 
f1_keywords:
 - "d3dumddi/SetDecodeRenderTarget"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetDecodeRenderTarget
product:
 - Windows
---

# PFND3DDDI_SETDECODERENDERTARGET callback function

## -description

The <i>SetDecodeRenderTarget</i> function sets the render target surface for decoding operations.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setdecoderendertarget">D3DDDIARG_SETDECODERENDERTARGET</a> structure that describes the decode render target surface.

## -returns

<i>SetDecodeRenderTarget</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The render target surface is successfully set.|
|E_OUTOFMEMORY|SetDecodeRenderTarget could not allocate the required memory for it to complete.|

## -remarks

The <i>SetDecodeRenderTarget</i> function can be called only outside of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodebeginframe">DecodeBeginFrame</a>/<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeendframe">DecodeEndFrame</a> block. 

Decode render targets are always created atomically through calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function, where all of the decode buffers are indexes within a single resource. All decode render targets are created by setting the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_resourceflags">D3DDDI_RESOURCEFLAGS</a>.<b>DecodeRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setdecoderendertarget">D3DDDIARG_SETDECODERENDERTARGET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_resourceflags">D3DDDI_RESOURCEFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodebeginframe">DecodeBeginFrame</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeendframe">DecodeEndFrame</a>

