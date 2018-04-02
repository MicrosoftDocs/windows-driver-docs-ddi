---
UID: NS:d3d10umddi.D3D11_1DDI_CERTIFICATE_INFO
title: D3D11_1DDI_CERTIFICATE_INFO
author: windows-driver-content
description: Specifies a cryptographic session certificate or authenticated channel.
old-location: display\d3d11_1ddi_certificate_info.htm
old-project: display
ms.assetid: 9a687c45-2201-483c-b1ad-958b9f651e54
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_CERTIFICATE_INFO, D3D11_1DDI_CERTIFICATE_INFO structure [Display Devices], d3d10umddi/D3D11_1DDI_CERTIFICATE_INFO, display.d3d11_1ddi_certificate_info
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_CERTIFICATE_INFO
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_CERTIFICATE_INFO
---

# D3D11_1DDI_CERTIFICATE_INFO structure


## -description


Specifies a cryptographic  session certificate or authenticated channel.


## -struct-fields




### -field CertificateType

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406438">D3D11_1DDI_CERTIFICATE_TYPE</a> value that specifies the type of authenticated certificate that is used to establish trust and perform a key exchange.


#### - ChannelType

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406343">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a> value that specifies the type of Direct3D authenticated channel.


#### - CryptoSessionType

A GUID that indicates the cryptographic session.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406343">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406438">D3D11_1DDI_CERTIFICATE_TYPE</a>
 

 

