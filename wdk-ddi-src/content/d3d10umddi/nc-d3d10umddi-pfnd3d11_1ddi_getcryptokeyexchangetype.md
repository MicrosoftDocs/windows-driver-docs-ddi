---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE
title: PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE (d3d10umddi.h)
description: Queries the type of key exchange that is supported by the cryptographic engine of the display adapter for a specified encryption algorithm and video decoder profile.
old-location: display\getcryptokeyexchangetype.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE callback function"]
ms.keywords: GetCryptoKeyExchangeType, GetCryptoKeyExchangeType callback function [Display Devices], PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE, PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE callback, d3d10umddi/GetCryptoKeyExchangeType, display.getcryptokeyexchangetype
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
 - PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE
 - d3d10umddi/PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - GetCryptoKeyExchangeType
product:
 - Windows
---

# PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE callback function


## -description

Queries the type of key exchange that is supported by the cryptographic engine of the display adapter for a specified encryption algorithm and video decoder profile.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param pCryptoType

A pointer to a GUID that specifies the type of encryption algorithm to query.

### -param pDecodeProfile

A pointer to a GUID that specifies the decoder profile to query.

### -param Index

The zero-based index of the key exchange type.

### -param pKeyExchangeType

A pointer to a GUID that specifies the supported key exchange type for the specified index.

## -returns

<b>GetCryptoKeyExchangeType</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The content protection capabilities were queried successfully.|
|D3DERR_INVALID_CRYPTO|The encryption algorithm specified by the pCryptoType parameter is not supported.|

## -remarks

The <b>GetCryptoKeyExchangeType</b> function can be called to query the key exchange types for any index from 0 to (<b>D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS.KeyExchangeTypeCount</b>– 1). 

The <i>pCryptoType</i> parameter can contain one of the following values:

* D3DCRYPTOTYPE_AES128_CTR if the driver is configured to use the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher.

* D3DCRYPTOTYPE_PROPRIETARY if the driver is configured to use a proprietary encryption algorithm.

* NULL_GUID if the driver is not configured to use any encryption algorithm.

> [!NOTE]
> The Microsoft Direct3D runtime verifies that the  *pDecodeProfile*, *pCryptoType*, and *Index* parameter data is valid before it calls the *GetCryptoKeyExchangeType* function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcontentprotectioncaps">GetContentProtectionCaps</a>
