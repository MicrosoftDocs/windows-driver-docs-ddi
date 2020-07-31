---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
title: D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS (d3d10umddi.h)
description: Describes the content-protection capabilities of the user-mode display driver.
old-location: display\d3d11_1ddi_video_content_protection_caps.htm
ms.assetid: 31ff5dfc-72b1-4ce1-af83-cad3816a785c
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS structure"]
ms.keywords: D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS, D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS, display.d3d11_1ddi_video_content_protection_caps
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS"
 - "D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS
---

# D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS structure


## -description


Describes the content-protection capabilities of the user-mode display driver.


## -struct-fields




### -field Caps

A bitwise <b>OR</b> of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_content_protection_caps">D3D11_1DDI_CONTENT_PROTECTION_CAPS</a> enumeration.


### -field KeyExchangeTypeCount

The number of cryptographic key-exchange types that are supported by the driver. To get the list of key-exchange types, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype">GetCryptoKeyExchangeType</a> function.


### -field BlockAlignmentSize

The encyrption block size, in bytes. The size of data to be encrypted must be a multiple of this value.


### -field ProtectedMemorySize

The total amount of memory, in bytes, that can be used to hold protected surfaces.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_content_protection_caps">D3D11_1DDI_CONTENT_PROTECTION_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcryptokeyexchangetype">GetCryptoKeyExchangeType</a>
 

 

