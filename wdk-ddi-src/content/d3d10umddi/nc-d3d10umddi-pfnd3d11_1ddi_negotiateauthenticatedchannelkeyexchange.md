---
UID: NC:d3d10umddi.PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE
title: PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE
author: windows-driver-content
description: Establishes a session key for an authenticated channel.
old-location: display\negotiateauthenticatedchannelkeyexchange.htm
old-project: display
ms.assetid: a54a26d2-d38c-4e82-a3e9-7a17c0afff27
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
req.alt-api: pfnNegotiateAuthenticatedChannelKeyExchange
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

# PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE callback



## -description
Establishes a session key for an authenticated channel.





## -prototype

````
PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE pfnNegotiateAuthenticatedChannelKeyExchange;

HRESULT APIENTRY* pfnNegotiateAuthenticatedChannelKeyExchange(
  _In_ D3D10DDI_HDEVICE        hDevice,
  _In_ D3D11_1DDI_HAUTHCHANNEL hCAuthChannel,
  _In_ UINT                    DataSize,
  _In_ VOID                    *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCAuthChannel [in]

A handle to an authenticated channel object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.




### -param DataSize [in]

The size, in bytes, of the data in the <i>pData</i> array.




### -param pData [in]

A pointer to a byte array that contains the encrypted session key.


## -returns
<b>NegotiateAuthenticatedChannelKeyExchange</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The session key for the authenticated channel was negotiated successfully.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

 


## -remarks
The <i>pData</i> parameter references a buffer that contains a session key for the authenticated channel. This key buffer must contain 256 bytes of data and must be encrypted by using the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm with the public key from the authenticated channel certificate.

The key exchange for an authenticated channel is identical to the key exchange for the Output Protection Manager (OPM) interface. However,  the OPM key buffer contains additional data besides the session key.  


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

