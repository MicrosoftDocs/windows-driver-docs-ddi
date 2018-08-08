---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
author: windows-driver-content
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION.
old-location: display\d3d11_1ddi_authenticated_configure_crypto_session.htm
tech.root: display
ms.assetid: 667429cb-0db8-4139-af5a-c3275b68a507
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION, D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION, display.d3d11_1ddi_authenticated_configure_crypto_session
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
-	D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION structure


## -description


Contains input data for a call to the <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</b>.


## -struct-fields




### -field Parameters

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data. 


### -field DecodeHandle

A handle to the decoder device.




### -field CryptoSessionHandle

A handle to the cryptographic session.


### -field DeviceHandle

A handle to the Direct3D device.


## -see-also




<a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>
 

 

