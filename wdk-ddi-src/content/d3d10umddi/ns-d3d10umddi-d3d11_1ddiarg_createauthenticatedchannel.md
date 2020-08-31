---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
title: D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL (d3d10umddi.h)
description: Specifies the attributes of the authenticated channel to be created by the user-mode driver's CreateAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddiarg_createauthenticatedchannel.htm
ms.assetid: 0b3a20db-aa03-4017-a10a-ae84a6ed31c8
ms.date: 05/10/2018
keywords: ["D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL structure"]
ms.keywords: D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL, D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL structure [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL, display.d3d11_1ddiarg_createauthenticatedchannel
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
req.typenames: D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
f1_keywords:
 - D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
 - d3d10umddi/D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
---

# D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL structure


## -description

Specifies the attributes of the authenticated channel to be created by the user-mode driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a> function.

## -struct-fields

### -field ChannelType

Specifies the type of channel, as a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a> enumeration.

### -field hChannel

A handle to the authenticated channel object.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a>

