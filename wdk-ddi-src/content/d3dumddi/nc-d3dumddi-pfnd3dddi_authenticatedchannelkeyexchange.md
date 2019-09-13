---
UID: NC:d3dumddi.PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE
title: PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE (d3dumddi.h)
description: The AuthenticatedChannelKeyExchange function negotiates the session key.
old-location: display\authenticatedchannelkeyexchange.htm
tech.root: display
ms.assetid: 627f9689-1059-4f88-9005-9c7600dad686
ms.date: 05/10/2018
ms.keywords: AuthenticatedChannelKeyExchange, AuthenticatedChannelKeyExchange callback function [Display Devices], PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE, PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE callback, UserModeDisplayDriver_Functions_2882c4c2-3df6-4610-9f8f-83967c485457.xml, d3dumddi/AuthenticatedChannelKeyExchange, display.authenticatedchannelkeyexchange
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: AuthenticatedChannelKeyExchange is supported beginning with the Windows 7 operating system.
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
req.typenames: 
f1_keywords:
 - "d3dumddi/AuthenticatedChannelKeyExchange"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - AuthenticatedChannelKeyExchange
product:
 - Windows
---

# PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE callback function

## -description

The <b>AuthenticatedChannelKeyExchange</b> function negotiates the session key.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

pData [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_authenticatedchannelkeyexchange">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a> structure that describes a buffer that contains the session key, which the  authenticated channel uses.

## -returns

<b>AuthenticatedChannelKeyExchange</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The session key is successfully negotiated. | 
| **E_OUTOFMEMORY** | [AuthenticatedChannelKeyExchange](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_authenticatedchannelkeyexchange)  could not allocate the required memory for it to complete. |

## -remarks

The <b>pData</b> member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_authenticatedchannelkeyexchange">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a> structure points to a buffer that contains a secret key that an application previously RSAES-OAEP-encrypted with the public key from the driver's authenticated channel certificate. The actual size of the buffer is 256 bytes. This exchange is identical to how the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supporting-output-protection-manager">Output Protection Manager</a> (OPM) key exchange works, except the OPM buffer contains additional data besides the session key. The same certificate that is used for OPM key exchange can be used for the authenticated channel. 

The driver decrypts this secret key and uses the secret key in calls to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel">ConfigureAuthenticatedChannel</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel">QueryAuthenticatedChannel</a> functions to calculate One-key Cipher Block Chaining (CBC)-mode message authentication codes (OMACs).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_authenticatedchannelkeyexchange">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a>

