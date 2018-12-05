---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODEREXTENSION
title: PFND3D11_1DDI_VIDEODECODEREXTENSION
author: windows-driver-content
description: Performs an extended function for DirectX Video Acceleration (DXVA) decoding. This method enables extensions to the basic DXVA decoder functionality.
old-location: display\videodecoderextension.htm
ms.assetid: 0cfcc05a-77d7-4157-bd27-ba127afe3e92
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_VIDEODECODEREXTENSION, PFND3D11_1DDI_VIDEODECODEREXTENSION callback, d3d10umddi/pfnVideoDecoderExtension, display.videodecoderextension, pfnVideoDecoderExtension, pfnVideoDecoderExtension callback function [Display Devices]
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
-	pfnVideoDecoderExtension
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_VIDEODECODEREXTENSION callback function


## -description


Performs an extended function for DirectX Video Acceleration (DXVA) decoding. This method enables extensions to the basic DXVA decoder functionality.




## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDecoder* [in]

A handle to the video decoder object that was created through a call to the <a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a> function.

### -param *

*pExtension* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406330">D3D11_1DDIARG_VIDEODECODEREXTENSION</a> structure that contains data for the extended function.




## -returns



<b>VideoDecoderExtension</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The extension was performed successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|
 
## -see-also




<a href="https://msdn.microsoft.com/41254f99-1806-428c-8bf3-7e736dbeec84">CreateVideoDecoder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406330">D3D11_1DDIARG_VIDEODECODEREXTENSION</a>
 

 

