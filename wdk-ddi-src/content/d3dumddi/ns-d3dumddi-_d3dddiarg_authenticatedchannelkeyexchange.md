---
UID: NS:d3dumddi._D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
title: "_D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE"
author: windows-driver-content
description: The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses.
old-location: display\d3dddiarg_authenticatedchannelkeyexchange.htm
old-project: display
ms.assetid: 99a86339-62ce-48fd-a1f4-5c3061e624b5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure [Display Devices], UMDisplayDriver_param_Structs_2b02df7d-1bae-446f-b52a-0a9353114504.xml, _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, d3dumddi/D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, display.d3dddiarg_authenticatedchannelkeyexchange
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
---

# _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure


## -description


The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses. 


## -syntax


````
typedef struct _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE {
  HANDLE hChannel;
  UINT   DataSize;
  VOID   *pData;
} D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE;
````


## -struct-fields




### -field hChannel

[in] A handle to the authenticated channel that the runtime creates when the runtime calls the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a> function. 


### -field DataSize

[in/out] The size, in bytes, of the data that the <b>pData</b> member points to. 


### -field pData

[in/out] A pointer to a buffer that contains the session key. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_authenticatedchannelkeyexchange.md">AuthenticatedChannelKeyExchange</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a>



 

 


