---
UID: NS:d3dumddi._D3DDDIARG_CREATEAUTHENICATEDCHANNEL
title: _D3DDDIARG_CREATEAUTHENICATEDCHANNEL (d3dumddi.h)
description: The D3DDDIARG_CREATEAUTHENTICATEDCHANNEL structure identifies a channel to create.
old-location: display\d3dddiarg_createauthenticatedchannel.htm
tech.root: display
ms.assetid: 00f8fbbc-1a4d-4cfe-8b87-fd70bf5a2d48
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CREATEAUTHENTICATEDCHANNEL, D3DDDIARG_CREATEAUTHENTICATEDCHANNEL structure [Display Devices], UMDisplayDriver_param_Structs_3cdac44d-7cac-43f6-80f5-dd601183fa8b.xml, _D3DDDIARG_CREATEAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_CREATEAUTHENTICATEDCHANNEL, display.d3dddiarg_createauthenticatedchannel
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CREATEAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_CREATEAUTHENTICATEDCHANNEL
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_CREATEAUTHENICATEDCHANNEL structure


## -description


The D3DDDIARG_CREATEAUTHENTICATEDCHANNEL structure identifies a channel to create. 


## -struct-fields




### -field ChannelType

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff549536">DDIAUTHENTICATEDCHANNELTYPE</a>-typed value that indicates the channel type to create. This member can be one of the following values.

| **Value** | **Meaning** | 
|:--|:--|
| DDIAUTHENTICATEDCHANNEL_DRIVER_SOFTWARE (2) | The authenticated-channel type is software. | 
| DDIAUTHENTICATEDCHANNEL_DRIVER_HARDWARE (3) | The authenticated-channel type is hardware. | 


### -field hChannel

[out] A handle to the channel. The user-mode display driver's <a href="https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889">CreateAuthenticatedChannel</a> function returns this handle to the Microsoft Direct3D runtime. 


## -see-also




<a href="https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889">CreateAuthenticatedChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549536">DDIAUTHENTICATEDCHANNELTYPE</a>
 

 

