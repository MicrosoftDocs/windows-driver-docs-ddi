---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATECRYPTOSESSION
title: D3D11_1DDIARG_CREATECRYPTOSESSION
author: windows-driver-content
description: Specifies the attributes of the cryptographic session to be created by the user-mode driver's CreateCryptoSession function.
old-location: display\d3d11_1ddiarg_createcryptosession.htm
old-project: display
ms.assetid: 9e63a4eb-050b-4f12-ad43-00e62021abd3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDIARG_CREATECRYPTOSESSION, D3D11_1DDIARG_CREATECRYPTOSESSION structure [Display Devices], D3D11_1DDI_CRYPTO_TYPE_AES128_CTR, D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY, D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION, d3d10umddi/D3D11_1DDIARG_CREATECRYPTOSESSION, display.d3d11_1ddiarg_createcryptosession
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDIARG_CREATECRYPTOSESSION
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATECRYPTOSESSION
---

# D3D11_1DDIARG_CREATECRYPTOSESSION structure


## -description


Specifies the attributes of the cryptographic session to be created by the user-mode driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.


## -struct-fields




### -field CryptoType

a GUID that indicates the encryption type, which the driver uses for the encryption session that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function creates. The GUID can be one of the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="D3D11_1DDI_CRYPTO_TYPE_AES128_CTR"></a><a id="d3d11_1ddi_crypto_type_aes128_ctr"></a><dl>
<dt><b>D3D11_1DDI_CRYPTO_TYPE_AES128_CTR</b></dt>
</dl>
</td>
<td width="60%">
A 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher.

</td>
</tr>
<tr>
<td width="40%"><a id="D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY"></a><a id="d3d11_1ddi_crypto_type_proprietary"></a><dl>
<dt><b>D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY</b></dt>
</dl>
</td>
<td width="60%">
A proprietary encryption algorithm.

</td>
</tr>
</table>
 


### -field DecodeProfile

A GUID that specifies the DirectX Video Acceleration (DXVA) decode profile that the driver uses for the encryption session that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function creates. For a list of possible values, see <b>CreateCryptoSession</b>. If DXVA decoding will not be used, set this parameter to <b>NULL_GUID</b>.


### -field KeyExchangeType

A GUID that specifies the type of key exchange.
The following GUID is defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP"></a><a id="d3d11_1ddi_key_exchange_rsaes_oaep"></a><dl>
<dt><b>D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP</b></dt>
</dl>
</td>
<td width="60%">
The caller will create the session key, encrypt it with RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) by using the driver's public key, and pass the session key to the driver.

</td>
</tr>
<tr>
<td width="40%"><a id="D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION"></a><a id="d3dwddm2_0ddi_key_exchange_hw_protection"></a><dl>
<dt><b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION</b></dt>
</dl>
</td>
<td width="60%">
The crypto session will be used purely for communication between user mode DRM component and the secure execution environment.



When this GUID is specified, the following DDIs should not be called for the crypto session:

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451654">GetCertificateSize</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451652">GetCertificate</a>
</li>
<li>
<a href="https://msdn.microsoft.com/a92bfff7-8af6-48c3-9e7f-95b9426aaaf2">EncryptionBlt</a>
</li>
<li>
<a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451696">StartSessionKeyRefresh</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451648">FinishSessionKeyRefresh</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451660">GetEncryptionBltKey</a>
</li>
</ul>

The DRM commands are sent to the user mode driver by calling the <a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a> function where the data passed is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn894610">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a> structure.


</td>
</tr>
</table>
 

