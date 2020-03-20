---
UID: NC:d3dumddi.PFND3DDDI_SETVIDEOPROCESSRENDERTARGET
title: PFND3DDDI_SETVIDEOPROCESSRENDERTARGET (d3dumddi.h)
description: The SetVideoProcessRenderTarget function sets the render target surface that is used for video processing.
old-location: display\setvideoprocessrendertarget.htm
tech.root: display
ms.assetid: 8aa7e23e-f52e-4252-9f22-56ce523f6cba
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETVIDEOPROCESSRENDERTARGET callback function"]
ms.keywords: PFND3DDDI_SETVIDEOPROCESSRENDERTARGET, PFND3DDDI_SETVIDEOPROCESSRENDERTARGET callback, SetVideoProcessRenderTarget, SetVideoProcessRenderTarget callback function [Display Devices], UserModeDisplayDriver_Functions_8ce2d981-2c69-45e9-a2e2-eba9026be1a0.xml, d3dumddi/SetVideoProcessRenderTarget, display.setvideoprocessrendertarget
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
 - "d3dumddi/SetVideoProcessRenderTarget"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetVideoProcessRenderTarget
product:
 - Windows
---

# PFND3DDDI_SETVIDEOPROCESSRENDERTARGET callback function

## -description

The <i>SetVideoProcessRenderTarget</i> function sets the render target surface that is used for video processing.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setvideoprocessrendertarget">D3DDDIARG_SETVIDEOPROCESSRENDERTARGET</a> structure that describes the render target surface that is used for video processing.

## -returns

<i>SetVideoProcessRenderTarget</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The render target surface is successfully set.|
|E_OUTOFMEMORY|SetVideoProcessRenderTarget could not allocate the required memory for it to complete.|

## -remarks

<i>SetVideoProcessRenderTarget</i> can be called only outside of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_videoprocessbeginframe">VideoProcessBeginFrame</a>/<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_videoprocessendframe">VideoProcessEndFrame</a> block. 

All video processing render targets are created by setting the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_resourceflags">D3DDDI_RESOURCEFLAGS</a>.<b>VideoProcessRenderTarget</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> structure in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setvideoprocessrendertarget">D3DDDIARG_SETVIDEOPROCESSRENDERTARGET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_resourceflags">D3DDDI_RESOURCEFLAGS</a>

