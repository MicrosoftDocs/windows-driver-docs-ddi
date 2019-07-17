---
UID: NE:d3d10umddi.D3D11_1DDI_CERTIFICATE_TYPE
title: D3D11_1DDI_CERTIFICATE_TYPE (d3d10umddi.h)
description: Specifies the type of authenticated certificate that is used to establish trust and perform a key exchange.
old-location: display\d3d11_1ddi_certificate_type.htm
ms.assetid: e95573c9-0ea7-4ad2-9e7e-d75761e98be6
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_CERTIFICATE_TYPE, D3D11_1DDI_CERTIFICATE_TYPE enumeration [Display Devices], D3D11_1DDI_CERTIFICATE_TYPE_AUTHENTICATED_CHANNEL, D3D11_1DDI_CERTIFICATE_TYPE_CRYPTO_SESSION, d3d10umddi/D3D11_1DDI_CERTIFICATE_TYPE, d3d10umddi/D3D11_1DDI_CERTIFICATE_TYPE_AUTHENTICATED_CHANNEL, d3d10umddi/D3D11_1DDI_CERTIFICATE_TYPE_CRYPTO_SESSION, display.d3d11_1ddi_certificate_type
ms.topic: enum
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_CERTIFICATE_TYPE"
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
- D3D11_1DDI_CERTIFICATE_TYPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_CERTIFICATE_TYPE
---

# D3D11_1DDI_CERTIFICATE_TYPE enumeration


## -description


Specifies the type of authenticated certificate that is used to establish trust and perform a key exchange. This type is used by callers of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificate">GetCertificate</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize">GetCertificateSize</a> functions.


## -enum-fields




### -field D3D11_1DDI_CERTIFICATE_TYPE_AUTHENTICATED_CHANNEL

The certificate is used for an authenticated channel.


### -field D3D11_1DDI_CERTIFICATE_TYPE_CRYPTO_SESSION

The certificate is used for a  cryptographic session.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificate">GetCertificate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize">GetCertificateSize</a>
 

 

