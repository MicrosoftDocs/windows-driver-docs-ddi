---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATECRYPTOSESSION
title: D3D11_1DDIARG_CREATECRYPTOSESSION
description: Specifies the attributes of the cryptographic session to be created by the user-mode driver's CreateCryptoSession function.
old-location: display\d3d11_1ddiarg_createcryptosession.htm
ms.assetid: 9e63a4eb-050b-4f12-ad43-00e62021abd3
ms.date: 05/10/2018
ms.keywords: D3D11_1DDIARG_CREATECRYPTOSESSION, D3D11_1DDIARG_CREATECRYPTOSESSION structure [Display Devices], D3D11_1DDI_CRYPTO_TYPE_AES128_CTR, D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY, D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION, d3d10umddi/D3D11_1DDIARG_CREATECRYPTOSESSION, display.d3d11_1ddiarg_createcryptosession
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
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_CREATECRYPTOSESSION
---

# D3D11_1DDIARG_CREATECRYPTOSESSION structure


## -description


Specifies the attributes of the cryptographic session to be created by the user-mode driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.


## -struct-fields




### -field CryptoType

a GUID that indicates the encryption type, which the driver uses for the encryption session that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function creates. The GUID can be one of the following:

|Value|Meaning|
|--- |--- |
|D3D11_1DDI_CRYPTO_TYPE_AES128_CTR|A 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher.|
|D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY|A proprietary encryption algorithm.|
 


### -field DecodeProfile

A GUID that specifies the DirectX Video Acceleration (DXVA) decode profile that the driver uses for the encryption session that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function creates. For a list of possible values, see <b>CreateCryptoSession</b>. If DXVA decoding will not be used, set this parameter to <b>NULL_GUID</b>.


### -field KeyExchangeType

A GUID that specifies the type of key exchange.
The following GUID is defined.


| **Value** | **Meaning** |
|:---|:---|
| **D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP** | The caller will create the session key, encrypt it with RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) by using the driver's public key, and pass the session key to the driver. | 
| **D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION** | The crypto session will be used purely for communication between user mode DRM component and the secure execution environment.<br/>When this GUID is specified, the following DDIs should not be called for the crypto session:<br/> [GetCertificateSize](https://msdn.microsoft.com/library/windows/hardware/hh451654), [GetCertificate](https://msdn.microsoft.com/library/windows/hardware/hh451652), [EncryptionBlt](https://msdn.microsoft.com/a92bfff7-8af6-48c3-9e7f-95b9426aaaf2), [DecryptionBlt](https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110), [StartSessionKeyRefresh](https://msdn.microsoft.com/library/windows/hardware/hh451696), [FinishSessionKeyRefresh](https://msdn.microsoft.com/library/windows/hardware/hh451648), [GetEncryptionBltKey](https://msdn.microsoft.com/library/windows/hardware/hh451660)<br/>The DRM commands are sent to the user mode driver by calling the [NegotiateCryptoSessionKeyExchange](https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b)  function where the data passed is a pointer to a [D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA](https://msdn.microsoft.com/library/windows/hardware/dn894610) structure. | 

