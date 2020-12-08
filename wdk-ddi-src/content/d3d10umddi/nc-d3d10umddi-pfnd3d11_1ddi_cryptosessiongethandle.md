---
UID: NC:d3d10umddi.PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE
title: PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE (d3d10umddi.h)
description: Returns a handle for a cryptographic session.
old-location: display\cryptosessiongethandle.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE callback function"]
ms.keywords: CryptoSessionGetHandle, CryptoSessionGetHandle callback function [Display Devices], PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE, PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE callback, d3d10umddi/CryptoSessionGetHandle, display.cryptosessiongethandle
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
 - PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE
 - d3d10umddi/PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CryptoSessionGetHandle
product:
 - Windows
---

# PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE callback function


## -description

Returns a handle for a cryptographic session.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hCryptoSession

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>.

### -param pHandle

A handle that is created by the driver for the cryptographic session.

## -returns

<b>CryptoSessionGetHandle</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The cryptographic session handle was returned successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

The <b>CryptoSessionGetHandle</b> function returns a driver-specified handle for the cryptographic session. This handle is used by the application when it associates the cryptographic session with the video decoder. This enables the decoder to decrypt data that is encrypted by using this session.


This function allows the driver to define its own handle to its state data for the cryptographic session. This bypasses any handle mapping that may be performed by the Direct3D runtime.

<div class="alert"><b>Note</b>  Drivers can return the same handle in the <i>pHandle</i> parameter that was passed  in the <i>hCryptoSession</i> parameter.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>
