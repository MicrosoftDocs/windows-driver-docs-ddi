---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL (d3d10umddi.h)
description: Releases resources for the authenticated channel that were created through a call to the CreateAuthenticatedChannel(D3D11_1) function.
old-location: display\destroyauthenticatedchannel1.htm
ms.assetid: 3eebda5e-72c6-4167-a886-58e877551923
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL callback function"]
ms.keywords: PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL, PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL callback, d3d10umddi/pfnDestroyAuthenticatedChannel, display.destroyauthenticatedchannel1, display.pfndestroyauthenticatedchannel1, pfnDestroyAuthenticatedChannel, pfnDestroyAuthenticatedChannel callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL
 - d3d10umddi/PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnDestroyAuthenticatedChannel
product:
 - Windows
---

# PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL callback function


## -description

Releases resources for the authenticated channel that were created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a> function.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hAuthChannel

A handle to the driver's private data for the authenticated channel. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel">CreateAuthenticatedChannel(D3D11_1)</a>

