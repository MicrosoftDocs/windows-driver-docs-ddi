---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATECRYPTOSESSION
title: D3D11_1DDIARG_CREATECRYPTOSESSION (d3d10umddi.h)
description: Specifies the attributes of the cryptographic session to be created by the user-mode driver's CreateCryptoSession function.
old-location: display\d3d11_1ddiarg_createcryptosession.htm
ms.date: 05/10/2018
keywords: ["D3D11_1DDIARG_CREATECRYPTOSESSION structure"]
ms.keywords: D3D11_1DDIARG_CREATECRYPTOSESSION, D3D11_1DDIARG_CREATECRYPTOSESSION structure [Display Devices], D3D11_1DDI_CRYPTO_TYPE_AES128_CTR, D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY, D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION, d3d10umddi/D3D11_1DDIARG_CREATECRYPTOSESSION, display.d3d11_1ddiarg_createcryptosession
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_CREATECRYPTOSESSION
f1_keywords:
 - D3D11_1DDIARG_CREATECRYPTOSESSION
 - d3d10umddi/D3D11_1DDIARG_CREATECRYPTOSESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDIARG_CREATECRYPTOSESSION
---

# D3D11_1DDIARG_CREATECRYPTOSESSION structure


## -description

Specifies the attributes of the cryptographic session to be created by the user-mode driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function.

## -struct-fields

### -field CryptoType

a GUID that indicates the encryption type, which the driver uses for the encryption session that the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function creates. The GUID can be one of the following:

|Value|Meaning|
|--- |--- |
|D3D11_1DDI_CRYPTO_TYPE_AES128_CTR|A 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher.|
|D3D11_1DDI_CRYPTO_TYPE_PROPRIETARY|A proprietary encryption algorithm.|

### -field DecodeProfile

A GUID that specifies the DirectX Video Acceleration (DXVA) decode profile that the driver uses for the encryption session that the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function creates. For a list of possible values, see <b>CreateCryptoSession</b>. If DXVA decoding will not be used, set this parameter to <b>NULL_GUID</b>.

### -field KeyExchangeType

A GUID that specifies the type of key exchange.
The following GUID is defined.


| **Value** | **Meaning** |
|:---|:---|
| **D3D11_1DDI_KEY_EXCHANGE_RSAES_OAEP** | The caller will create the session key, encrypt it with RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) by using the driver's public key, and pass the session key to the driver. | 
| **D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION** | The crypto session will be used purely for communication between user mode DRM component and the secure execution environment.<br/>When this GUID is specified, the following DDIs should not be called for the crypto session:<br/> [GetCertificateSize](./nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md), [GetCertificate](./nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md), [EncryptionBlt](../d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt.md), [DecryptionBlt](../d3dumddi/nc-d3dumddi-pfnd3dddi_decryptionblt.md), [StartSessionKeyRefresh](./nc-d3d10umddi-pfnd3d11_1ddi_startsessionkeyrefresh.md), [FinishSessionKeyRefresh](./nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh.md), [GetEncryptionBltKey](./nc-d3d10umddi-pfnd3d11_1ddi_getencryptionbltkey.md)<br/>The DRM commands are sent to the user mode driver by calling the [NegotiateCryptoSessionKeyExchange](./nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md)  function where the data passed is a pointer to a [D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA](./ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data.md) structure. |
