---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL
author: windows-driver-content
description: Releases resources for the authenticated channel that were created through a call to the CreateAuthenticatedChannel(D3D11_1) function.
old-location: display\destroyauthenticatedchannel1.htm
old-project: display
ms.assetid: 3eebda5e-72c6-4167-a886-58e877551923
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL, PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL callback, d3d10umddi/pfnDestroyAuthenticatedChannel, display.destroyauthenticatedchannel1, display.pfndestroyauthenticatedchannel1, pfnDestroyAuthenticatedChannel, pfnDestroyAuthenticatedChannel callback function [Display Devices]
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
-	pfnDestroyAuthenticatedChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_DESTROYAUTHENTICATEDCHANNEL callback function


## -description


Releases resources for the authenticated channel that were created through a call to the <a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a> function.



## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hAuthChannel [in]

A handle to the driver's private data for the authenticated channel. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a>
 

 

