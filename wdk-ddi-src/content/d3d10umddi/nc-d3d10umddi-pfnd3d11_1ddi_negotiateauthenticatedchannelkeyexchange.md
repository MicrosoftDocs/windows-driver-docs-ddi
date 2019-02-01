---
UID: NC:d3d10umddi.PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE
title: PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE (d3d10umddi.h)
description: Establishes a session key for an authenticated channel.
old-location: display\negotiateauthenticatedchannelkeyexchange.htm
ms.assetid: a54a26d2-d38c-4e82-a3e9-7a17c0afff27
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE, PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE callback, d3d10umddi/pfnNegotiateAuthenticatedChannelKeyExchange, display.negotiateauthenticatedchannelkeyexchange, pfnNegotiateAuthenticatedChannelKeyExchange, pfnNegotiateAuthenticatedChannelKeyExchange callback function [Display Devices]
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
-	pfnNegotiateAuthenticatedChannelKeyExchange
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_NEGOTIATEAUTHENTICATEDCHANNELKEYEXCHANGE callback function


## -description


Establishes a session key for an authenticated channel.




## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCAuthChannel [in]

A handle to an authenticated channel object that was created through a call to the <a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a> function.




### -param DataSize [in]

The size, in bytes, of the data in the <i>pData</i> array.




### -param *pData [in]

A pointer to a byte array that contains the encrypted session key.


## -returns



<b>NegotiateAuthenticatedChannelKeyExchange</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The session key for the authenticated channel was negotiated successfully.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|
 




## -remarks



The <i>pData</i> parameter references a buffer that contains a session key for the authenticated channel. This key buffer must contain 256 bytes of data and must be encrypted by using the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm with the public key from the authenticated channel certificate.

The key exchange for an authenticated channel is identical to the key exchange for the Output Protection Manager (OPM) interface. However,  the OPM key buffer contains additional data besides the session key.  

> [!NOTE]
> The same certificate can be used for the authenticated channel and OPM session key.



## -see-also




<a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a>
 

 

