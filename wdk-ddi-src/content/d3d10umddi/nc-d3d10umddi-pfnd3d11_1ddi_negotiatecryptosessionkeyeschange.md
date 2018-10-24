---
UID: NC:d3d10umddi.PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE
title: PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE
author: windows-driver-content
description: Establishes a session key for a cryptographic session object.
old-location: display\negotiatecryptosessionkeyexchange.htm
ms.assetid: a48dcbae-3236-4523-bc14-4be694da9a7b
ms.date: 05/10/2018
ms.keywords: NegotiateCryptoSessionKeyExchange, NegotiateCryptoSessionKeyExchange callback function [Display Devices], PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE, PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE callback, d3d10umddi/NegotiateCryptoSessionKeyExchange, display.negotiatecryptosessionkeyexchange
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
-	NegotiateCryptoSessionKeyExchange
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE callback function


## -description


Establishes a session key for a cryptographic session object.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function. 




### -param DataSize [in]

The size, in bytes, of the data in the <i>pData</i> array.




### -param *pData [in]

A pointer to a byte array that contains the encrypted session key.


## -returns



<i>NegotiateCryptoSessionKeyExchange</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The session key for the cryptographic session was negotiated successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The <i>pData</i> parameter references a buffer that contains a session key for the cryptographic session. The key exchange mechanism depends on the type of the encryption algorithm that is used by the cryptographic session.

For sessions that use the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm, the key buffer must contain 256 bytes of data and must be encrypted by using the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm with the public key from the cryptographic session certificate.

The key exchange for a cryptographic session is identical to the key exchange for the Output Protection Manager (OPM) interface. However,  the OPM key buffer contains additional data besides the session key.  

<div class="alert"><b>Note</b>  The same certificate can be used for the cryptographic session and OPM session key.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>
 

 

