---
UID: NC:d3dumddi.PFND3DDDI_CREATEAUTHENTICATEDCHANNEL
title: PFND3DDDI_CREATEAUTHENTICATEDCHANNEL (d3dumddi.h)
description: The CreateAuthenticatedChannel function creates a channel that the Microsoft Direct3D runtime and the driver can use to set and query protections.
old-location: display\createauthenticatedchannel.htm
tech.root: display
ms.assetid: 0a565bff-fc6f-41c1-a6fd-3a82dd0d7889
ms.date: 05/10/2018
ms.keywords: CreateAuthenticatedChannel, CreateAuthenticatedChannel callback function [Display Devices], PFND3DDDI_CREATEAUTHENTICATEDCHANNEL, PFND3DDDI_CREATEAUTHENTICATEDCHANNEL callback, UserModeDisplayDriver_Functions_5645674c-e4e5-4b9c-9cbf-588b829df423.xml, d3dumddi/CreateAuthenticatedChannel, display.createauthenticatedchannel
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateAuthenticatedChannel is supported beginning with the Windows 7 operating system.
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	CreateAuthenticatedChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEAUTHENTICATEDCHANNEL callback function


## -description


The <b>CreateAuthenticatedChannel</b> function creates a channel that the Microsoft Direct3D runtime and the driver can use to set and query protections. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542918">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Direct3D runtime can use. 


## -returns


<b>CreateAuthenticatedChannel</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The channel is successfully created. | 
| **E_OUTOFMEMORY** | [CreateAuthenticatedChannel](https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889)  could not allocate the required memory for it to complete. | 
| **D3DDDIERR_NOTAVAILABLE** | The driver does not support the channel type that is specified in the ChannelType member of the [D3DDDIARG_CREATEAUTHENTICATEDCHANNEL](https://msdn.microsoft.com/library/windows/hardware/ff542918) structure that the pData parameter points to. |


## -remarks



The runtime passes the handle to the authenticated channel that the driver returns in the <b>ChannelType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542918">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a> structure in all subsequent calls that require the handle. 

The driver must keep track of the display device (<i>hDevice</i>) that was used to create the authenticated channel. The driver should fail all subsequent calls that use this created authenticated channel (for example, the <a href="https://msdn.microsoft.com/627f9689-1059-4f88-9005-9c7600dad686">AuthenticatedChannelKeyExchange</a> function) if the display device that is specified in those calls is different from the display device that was used to create the authenticated channel. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542918">D3DDDIARG_CREATEAUTHENTICATEDCHANNEL</a>
 

 

