---
UID: NE:d3d10umddi.D3D11_1DDI_CERTIFICATE_TYPE
title: D3D11_1DDI_CERTIFICATE_TYPE
author: windows-driver-content
description: Specifies the type of authenticated certificate that is used to establish trust and perform a key exchange.
old-location: display\d3d11_1ddi_certificate_type.htm
old-project: display
ms.assetid: e95573c9-0ea7-4ad2-9e7e-d75761e98be6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_CERTIFICATE_TYPE_CRYPTO_SESSION, d3d10umddi/D3D11_1DDI_CERTIFICATE_TYPE, D3D11_1DDI_CERTIFICATE_TYPE_AUTHENTICATED_CHANNEL, d3d10umddi/D3D11_1DDI_CERTIFICATE_TYPE_CRYPTO_SESSION, d3d10umddi/D3D11_1DDI_CERTIFICATE_TYPE_AUTHENTICATED_CHANNEL, D3D11_1DDI_CERTIFICATE_TYPE, display.d3d11_1ddi_certificate_type, D3D11_1DDI_CERTIFICATE_TYPE enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D11_1DDI_CERTIFICATE_TYPE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_CERTIFICATE_TYPE
---

# D3D11_1DDI_CERTIFICATE_TYPE enumeration


## -description


Specifies the type of authenticated certificate that is used to establish trust and perform a key exchange. This type is used by callers of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md">GetCertificate</a> and <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md">GetCertificateSize</a> functions.


## -syntax


````
typedef enum D3D11_1DDI_CERTIFICATE_TYPE { 
  D3D11_1DDI_CERTIFICATE_TYPE_AUTHENTICATED_CHANNEL  = 1,
  D3D11_1DDI_CERTIFICATE_TYPE_CRYPTO_SESSION         = 2
} D3D11_1DDI_CERTIFICATE_TYPE;
````


## -enum-fields




### -field D3D11_1DDI_CERTIFICATE_TYPE_AUTHENTICATED_CHANNEL

The certificate is used for an authenticated channel.


### -field D3D11_1DDI_CERTIFICATE_TYPE_CRYPTO_SESSION

The certificate is used for a  cryptographic session.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md">GetCertificate</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md">GetCertificateSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_CERTIFICATE_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

