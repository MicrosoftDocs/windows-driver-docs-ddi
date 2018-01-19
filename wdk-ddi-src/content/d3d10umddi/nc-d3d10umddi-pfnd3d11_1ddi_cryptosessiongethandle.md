---
UID: NC:d3d10umddi.PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE
title: PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE
author: windows-driver-content
description: Returns a handle for a cryptographic session.
old-location: display\cryptosessiongethandle.htm
old-project: display
ms.assetid: 30700af0-79e8-4808-bec8-94f5e5152bcc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CryptoSessionGetHandle
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE callback



## -description
Returns a handle for a cryptographic session.



## -prototype

````
PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE CryptoSessionGetHandle;

HRESULT APIENTRY* CryptoSessionGetHandle(
  _In_  D3D10DDI_HDEVICE          hDevice,
  _In_  D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  _Out_ HANDLE                    *pHandle
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>.


### -param pHandle [out]

A handle that is created by the driver for the cryptographic session.


## -returns
<b>CryptoSessionGetHandle</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The cryptographic session handle was returned successfully.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>The graphics adapter was removed.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

 


## -remarks
The <b>CryptoSessionGetHandle</b> function returns a driver-specified handle for the cryptographic session. This handle is used by the application when it associates the cryptographic session with the video decoder. This enables the decoder to decrypt data that is encrypted by using this session.


This function allows the driver to define its own handle to its state data for the cryptographic session. This bypasses any handle mapping that may be performed by the Direct3D runtime.


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

