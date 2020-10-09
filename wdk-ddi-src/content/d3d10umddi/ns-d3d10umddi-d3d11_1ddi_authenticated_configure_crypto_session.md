---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION (d3d10umddi.h)
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION.
old-location: display\d3d11_1ddi_authenticated_configure_crypto_session.htm
ms.assetid: 667429cb-0db8-4139-af5a-c3275b68a507
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION structure"]
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION, D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION, display.d3d11_1ddi_authenticated_configure_crypto_session
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
f1_keywords:
 - D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
 - d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION structure


## -description

Contains input data for a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</b>.

## -struct-fields

### -field Parameters

A <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data.

### -field DecodeHandle

A handle to the decoder device.

### -field CryptoSessionHandle

A handle to the cryptographic session.

### -field DeviceHandle

A handle to the Direct3D device.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>