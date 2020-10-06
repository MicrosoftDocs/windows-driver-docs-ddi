---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
title: PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS (d3d10umddi.h)
description: Queries the available content protection for a specified encryption algorithm and video decoder profile.
old-location: display\getcontentprotectioncaps.htm
ms.assetid: 51024d63-f58c-45a7-bd6f-9f24a6805878
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback function"]
ms.keywords: PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS, PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback, d3d10umddi/pfnGetContentProtectionCaps, display.getcontentprotectioncaps, pfnGetContentProtectionCaps, pfnGetContentProtectionCaps callback function [Display Devices]
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
 - PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
 - d3d10umddi/PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnGetContentProtectionCaps
product:
 - Windows
---

# PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback function


## -description

Queries the available content protection for a specified encryption algorithm and video decoder profile.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param pCryptoType

A pointer to a GUID that specifies the type of encryption algorithm to query.

### -param pDecodeProfile

A pointer to a GUID that specifies the decoder profile to query.

### -param pCaps

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a> structure that contains the protection capabilities for the specified encryption algorithm and decoder profile.

## -returns

<b>GetContentProtectionCaps</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The content protection capabilities were queried successfully.|
|D3DERR_INVALID_CRYPTO|The encryption algorithm specified by the pCryptoType parameter is not supported.|

## -remarks

The *pCryptoType* parameter can contain one of the following values:

* D3DCRYPTOTYPE_AES128_CTR if the driver is configured to use the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher.

* D3DCRYPTOTYPE_PROPRIETARY if the driver is configured to use a proprietary encryption algorithm.

* NULL_GUID if the driver is not configured to use any encryption algorithm.

> [!NOTE]
> The Microsoft Direct3D runtime verifies that the  *pDecodeProfile* and *pCryptoType* parameter data is valid before it calls the [GetContentProtectionCaps]() function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>