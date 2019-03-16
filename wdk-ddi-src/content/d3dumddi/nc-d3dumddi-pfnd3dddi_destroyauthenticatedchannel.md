---
UID: NC:d3dumddi.PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL
title: PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL (d3dumddi.h)
description: The DestroyAuthenticatedChannel function releases resources for the authenticated channel that the CreateAuthenticatedChannel function creates.
old-location: display\destroyauthenticatedchannel.htm
tech.root: display
ms.assetid: ccea427b-e19e-433b-91b0-b40ce7c1da5a
ms.date: 05/10/2018
ms.keywords: DestroyAuthenticatedChannel, DestroyAuthenticatedChannel callback function [Display Devices], PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL, PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL callback, UserModeDisplayDriver_Functions_94df7fa0-966d-45e3-81b7-bae1f6ebac64.xml, d3dumddi/DestroyAuthenticatedChannel, display.destroyauthenticatedchannel
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyAuthenticatedChannel is supported beginning with the Windows 7 operating system.
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- DestroyAuthenticatedChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL callback function


## -description


The <b>DestroyAuthenticatedChannel</b> function releases resources for the authenticated channel that the <a href="https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889">CreateAuthenticatedChannel</a> function creates. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543022">D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL</a> structure that contains one member that specifies the handle to the authenticated channel to destroy. 


## -returns



<b>DestroyAuthenticatedChannel</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The authenticated channel is successfully destroyed.|
|E_OUTOFMEMORY|DestroyAuthenticatedChannel could not allocate the required memory for it to complete.|


## -remarks



The driver's <b>DestroyAuthenticatedChannel</b> function should disable any protections that were set through calls to the driver's <a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a> function with the D3DAUTHETICATEDCONFIGURE_PROTECTION and D3DAUTHENTICATEDCONFIGURE_ENCRYPTIONWHENACCESIBLE GUIDs set. However, the driver should not disable shared surface protection (D3DAUTHETICATEDCONFIGURE_SHAREDRESOURCE).




## -see-also




<a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a>



<a href="https://msdn.microsoft.com/0a565bff-fc6f-41c1-a6fd-3a82dd0d7889">CreateAuthenticatedChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543022">D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL</a>
 

 

