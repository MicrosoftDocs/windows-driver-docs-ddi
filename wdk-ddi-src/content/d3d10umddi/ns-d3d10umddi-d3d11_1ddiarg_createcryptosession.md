---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATECRYPTOSESSION
title: D3D11_1DDIARG_CREATECRYPTOSESSION
author: windows-driver-content
description: Specifies the attributes of the cryptographic session to be created by the user-mode driver's CreateCryptoSession function.
old-location: display\d3d11_1ddiarg_createcryptosession.htm
old-project: display
ms.assetid: 9e63a4eb-050b-4f12-ad43-00e62021abd3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 1, 3, A, C, D, D3D11_1DDIARG_CREATECRYPTOSESSION, D3D11_1DDIARG_CREATECRYPTOSESSION structure [Display Devices], D3D11_1DDI_CRYPTO_TYPE_AES128_CTR, D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY, D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION, E, G, I, N, O, P, R, S, T, Y, _, d3d10umddi/D3D11_1DDIARG_CREATECRYPTOSESSION, display.d3d11_1ddiarg_createcryptosession"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDIARG_CREATECRYPTOSESSION
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATECRYPTOSESSION
---

# D3D11_1DDIARG_CREATECRYPTOSESSION structure


## -description


Specifies the attributes of the cryptographic session to be created by the user-mode driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function.


## -syntax


````
typedef struct D3D11_1DDIARG_CREATECRYPTOSESSION {
  GUID CryptoType;
  GUID DecodeProfile;
  GUID KeyExchangeType;
} D3D11_1DDIARG_CREATECRYPTOSESSION;
````


## -struct-fields




### -field CryptoType

a GUID that indicates the encryption type, which the driver uses for the encryption session that the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function creates. The GUID can be one of the following:

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

A GUID that specifies the DirectX Video Acceleration (DXVA) decode profile that the driver uses for the encryption session that the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function creates. For a list of possible values, see <b>CreateCryptoSession</b>. If DXVA decoding will not be used, set this parameter to <b>NULL_GUID</b>.


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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md">GetCertificateSize</a>
</li>
<li>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md">GetCertificate</a>
</li>
<li>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_encryptionblt.md">EncryptionBlt</a>
</li>
<li>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a>
</li>
<li>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a>
</li>
<li>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a>
</li>
<li>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getencryptionbltkey.md">GetEncryptionBltKey</a>
</li>
</ul>

The DRM commands are sent to the user mode driver by calling the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a> function where the data passed is a pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a> structure.


</td>
</tr>
</table>
 

