---
UID: NS:d3dumddi._D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
title: _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE (d3dumddi.h)
description: The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses.
old-location: display\d3dddiarg_authenticatedchannelkeyexchange.htm
tech.root: display
ms.assetid: 99a86339-62ce-48fd-a1f4-5c3061e624b5
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure [Display Devices], UMDisplayDriver_param_Structs_2b02df7d-1bae-446f-b52a-0a9353114504.xml, _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, d3dumddi/D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, display.d3dddiarg_authenticatedchannelkeyexchange
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE is supported beginning with the Windows 7 operating system.
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
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
---

# _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure


## -description


The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses. 


## -struct-fields




### -field hChannel

[in] A handle to the authenticated channel that the runtime creates when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createauthenticatedchannel">CreateAuthenticatedChannel</a> function. 


### -field DataSize

[in/out] The size, in bytes, of the data that the <b>pData</b> member points to. 


### -field pData

[in/out] A pointer to a buffer that contains the session key. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_authenticatedchannelkeyexchange">AuthenticatedChannelKeyExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createauthenticatedchannel">CreateAuthenticatedChannel</a>
 

 

