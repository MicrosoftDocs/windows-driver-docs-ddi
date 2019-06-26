---
UID: NS:d3d10umddi.D3D11_1DDI_CERTIFICATE_INFO
title: D3D11_1DDI_CERTIFICATE_INFO (d3d10umddi.h)
description: Specifies a cryptographic session certificate or authenticated channel.
old-location: display\d3d11_1ddi_certificate_info.htm
ms.assetid: 9a687c45-2201-483c-b1ad-958b9f651e54
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_CERTIFICATE_INFO, D3D11_1DDI_CERTIFICATE_INFO structure [Display Devices], d3d10umddi/D3D11_1DDI_CERTIFICATE_INFO, display.d3d11_1ddi_certificate_info
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_CERTIFICATE_INFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_CERTIFICATE_INFO
---

# D3D11_1DDI_CERTIFICATE_INFO structure


## -description


Specifies a cryptographic  session certificate or authenticated channel.


## -struct-fields




### -field CertificateType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_certificate_type">D3D11_1DDI_CERTIFICATE_TYPE</a> value that specifies the type of authenticated certificate that is used to establish trust and perform a key exchange.


### -field ChannelType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a> value that specifies the type of Direct3D authenticated channel.


### -field CryptoSessionType

A GUID that indicates the cryptographic session.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_certificate_type">D3D11_1DDI_CERTIFICATE_TYPE</a>
 

 

