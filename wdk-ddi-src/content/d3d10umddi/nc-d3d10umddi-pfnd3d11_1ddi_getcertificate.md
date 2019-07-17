---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCERTIFICATE
title: PFND3D11_1DDI_GETCERTIFICATE (d3d10umddi.h)
description: Returns a certificate that the display miniport driver uses for either the cryptographic session certificate or authenticated channel.
old-location: display\getcertificate.htm
ms.assetid: b2ceaa6e-a952-4c2f-9594-289ebe24c62d
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_GETCERTIFICATE, PFND3D11_1DDI_GETCERTIFICATE callback, d3d10umddi/pfnGetCertificate, display.getcertificate, pfnGetCertificate, pfnGetCertificate callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnGetCertificate"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnGetCertificate
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_GETCERTIFICATE callback function


## -description


Returns a certificate that the display miniport driver uses for either the cryptographic  session certificate or authenticated channel.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCertificateInfo [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_certificate_info">D3D11_1DDI_CERTIFICATE_INFO</a> structure that specifies the cryptographic  session certificate or authenticated channel to return.


### -param CertificateSize [in]

The size, in bytes, of the buffer that is referenced by the <i>pCertificate</i> parameter.


### -param *pCertificate [out]

A pointer to a byte array that receives the driver's certificate chain.


## -returns



This callback function does not return a value.




## -remarks



Based on the data in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_certificate_info">D3D11_1DDI_CERTIFICATE_INFO</a> structure, <b>GetCertificate</b> returns the certificate for either the cryptographic session or the authenticated channel. The driver uses this certificate to establish trust and perform key exchange for the session or channel.

<div class="alert"><b>Note</b>  The size, in bytes, of a driver's certificate chain can be queried by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize">GetCertificateSize</a>.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_certificate_info">D3D11_1DDI_CERTIFICATE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize">GetCertificateSize</a>
 

 

