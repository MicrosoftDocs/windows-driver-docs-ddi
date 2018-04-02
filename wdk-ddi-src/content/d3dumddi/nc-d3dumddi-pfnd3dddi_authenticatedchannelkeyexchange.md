---
UID: NC:d3dumddi.PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE
title: PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE
author: windows-driver-content
description: The AuthenticatedChannelKeyExchange function negotiates the session key.
old-location: display\authenticatedchannelkeyexchange.htm
old-project: display
ms.assetid: 627f9689-1059-4f88-9005-9c7600dad686
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AuthenticatedChannelKeyExchange, AuthenticatedChannelKeyExchange callback function [Display Devices], PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE, UserModeDisplayDriver_Functions_2882c4c2-3df6-4610-9f8f-83967c485457.xml, d3dumddi/AuthenticatedChannelKeyExchange, display.authenticatedchannelkeyexchange
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	AuthenticatedChannelKeyExchange
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE callback


## -description


The <b>AuthenticatedChannelKeyExchange</b> function negotiates the session key. 


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542880">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a> structure that describes a buffer that contains the session key, which the  authenticated channel uses. 


## -returns



<b>AuthenticatedChannelKeyExchange</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The session key is successfully negotiated. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/627f9689-1059-4f88-9005-9c7600dad686">AuthenticatedChannelKeyExchange</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The <b>pData</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542880">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a> structure points to a buffer that contains a secret key that an application previously RSAES-OAEP-encrypted with the public key from the driver's authenticated channel certificate. The actual size of the buffer is 256 bytes. This exchange is identical to how the <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) key exchange works, except the OPM buffer contains additional data besides the session key. The same certificate that is used for OPM key exchange can be used for the authenticated channel. 

The driver decrypts this secret key and uses the secret key in calls to the driver's <a href="https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd">ConfigureAuthenticatedChannel</a> and <a href="https://msdn.microsoft.com/13b65b5a-9512-4d67-b629-479bdd74674e">QueryAuthenticatedChannel</a> functions to calculate One-key Cipher Block Chaining (CBC)-mode message authentication codes (OMACs). 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542880">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a>
 

 

