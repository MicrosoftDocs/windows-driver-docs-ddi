---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCERTIFICATE
title: PFND3D11_1DDI_GETCERTIFICATE
author: windows-driver-content
description: Returns a certificate that the display miniport driver uses for either the cryptographic session certificate or authenticated channel.
old-location: display\getcertificate.htm
old-project: display
ms.assetid: b2ceaa6e-a952-4c2f-9594-289ebe24c62d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_GETCERTIFICATE, d3d10umddi/pfnGetCertificate, display.getcertificate, pfnGetCertificate, pfnGetCertificate callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnGetCertificate
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_GETCERTIFICATE callback


## -description


Returns a certificate that the display miniport driver uses for either the cryptographic  session certificate or authenticated channel.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCertificateInfo [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406435">D3D11_1DDI_CERTIFICATE_INFO</a> structure that specifies the cryptographic  session certificate or authenticated channel to return.


### -param CertificateSize [in]

The size, in bytes, of the buffer that is referenced by the <i>pCertificate</i> parameter.


### -param *pCertificate [out]

A pointer to a byte array that receives the driver's certificate chain.


## -returns



This callback function does not return a value.




## -remarks



Based on the data in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406435">D3D11_1DDI_CERTIFICATE_INFO</a> structure, <b>GetCertificate</b> returns the certificate for either the cryptographic session or the authenticated channel. The driver uses this certificate to establish trust and perform key exchange for the session or channel.

<div class="alert"><b>Note</b>  The size, in bytes, of a driver's certificate chain can be queried by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451654">GetCertificateSize</a>.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406435">D3D11_1DDI_CERTIFICATE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451654">GetCertificateSize</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETCERTIFICATE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

