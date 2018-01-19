---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATECRYPTOSESSION
title: PFND3D11_1DDI_CREATECRYPTOSESSION
author: windows-driver-content
description: Creates a cryptographic session to encrypt video content that is sent to the display miniport driver.
old-location: display\createcryptosession1.htm
old-project: display
ms.assetid: 3c31efc3-b844-4e51-947d-b48f36020766
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
req.alt-api: CreateCryptoSession
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

# PFND3D11_1DDI_CREATECRYPTOSESSION callback



## -description
Creates a cryptographic session to encrypt video content that is sent to the display miniport driver.



## -prototype

````
PFND3D11_1DDI_CREATECRYPTOSESSION CreateCryptoSession;

HRESULT APIENTRY* CreateCryptoSession(
  _In_       D3D10DDI_HDEVICE                  hDevice,
  _In_ const D3D11_1DDIARG_CREATECRYPTOSESSION *pCreateData,
  _In_       D3D11_1DDI_HCRYPTOSESSION         hCryptoSession,
  _In_       D3D11_1DDI_HRTCRYPTOSESSION       hRTCryptoSession
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createcryptosession.md">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure. This structure specifies the attributes of the cryptographic session to be created.


### -param hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. For more information, see the Remarks section.


### -param hRTCryptoSession [in]

A handle to the cryptographic session that the driver should use when it calls back into the Direct3D runtime.


## -returns
Returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The authenticated channel was created successfully.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>The graphics adapter was removed.
<dl>
<dt><b>D3DDDIERR_UNSUPPORTEDCRYPTO</b></dt>
</dl>A cryptographic type was specified that is not supported by the decode profile.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

 


## -remarks
The Direct3D runtime calls <i>CreateCryptoSession</i> to create a cryptographic session that the runtime uses to manage a session key and to perform cryptographic operations for video content that is stored in protected memory. 


The  runtime calls <i>CreateCryptoSession</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize.md">CalcPrivateCryptoSessionSize</a> to determine the size in bytes for the private data that the driver requires for the cryptographic session. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the cryptographic session.

When the runtime  calls <i>CreateCryptoSession</i>, it passes the handle to the private data memory in the <i>hCryptoSession</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the cryptographic session. The driver should fail all subsequent calls that use this created cryptographic session, such as <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>, if the display device that is specified in those calls is different from the display device that was used to create the cryptographic session. 



If the <b>DecodeProfile</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createcryptosession.md">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure is set to <b>NULL_GUID</b>, the cryptographic session will not be used for DirectX Video Acceleration (DXVA) decoding. If <b>DecodeProfile</b> is not set to <b>NULL_GUID</b>, the driver should fail the call with <b>D3DDDIERR_UNSUPPORTEDCRYPTO</b> if the <b>CryptoType</b> member is set to a cryptographic type that is not supported by the decode profile.


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize.md">CalcPrivateCryptoSessionSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createcryptosession.md">D3D11_1DDIARG_CREATECRYPTOSESSION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATECRYPTOSESSION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

