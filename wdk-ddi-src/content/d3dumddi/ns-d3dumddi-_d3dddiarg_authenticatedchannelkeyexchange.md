---
UID: NS:d3dumddi._D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
title: _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE (d3dumddi.h)
description: The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses.
old-location: display\d3dddiarg_authenticatedchannelkeyexchange.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure"]
ms.keywords: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure [Display Devices], UMDisplayDriver_param_Structs_2b02df7d-1bae-446f-b52a-0a9353114504.xml, _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, d3dumddi/D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, display.d3dddiarg_authenticatedchannelkeyexchange
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
targetos: Windows
req.typenames: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
f1_keywords:
 - _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
 - d3dumddi/_D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
 - D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
 - d3dumddi/D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
 - D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
---

# _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure


## -description

The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses.

## -struct-fields

### -field hChannel [in]

A handle to the authenticated channel that the runtime creates when the runtime calls the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createauthenticatedchannel">CreateAuthenticatedChannel</a> function.

### -field DataSize [in/out]

The size, in bytes, of the data that the <b>pData</b> member points to.

### -field pData [in/out]

A pointer to a buffer that contains the session key.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_authenticatedchannelkeyexchange">AuthenticatedChannelKeyExchange</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createauthenticatedchannel">CreateAuthenticatedChannel</a>

