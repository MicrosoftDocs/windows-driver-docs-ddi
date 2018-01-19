---
UID: NS:wwan._WWAN_AUTH_SIM_RESPONSE
title: _WWAN_AUTH_SIM_RESPONSE
author: windows-driver-content
description: The WWAN_AUTH_SIM_RESPONSE structure represents a response to a SIM authentication challenge.
old-location: netvista\wwan_auth_sim_response.htm
old-project: netvista
ms.assetid: C259CA95-D119-47EB-A32D-9C9E284B6CD4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_AUTH_SIM_RESPONSE, *PWWAN_AUTH_SIM_RESPONSE, WWAN_AUTH_SIM_RESPONSE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_AUTH_SIM_RESPONSE
req.alt-loc: wwan.h
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
req.typenames: *PWWAN_AUTH_SIM_RESPONSE, WWAN_AUTH_SIM_RESPONSE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_SIM_RESPONSE structure



## -description
The WWAN_AUTH_SIM_RESPONSE structure represents a response to a SIM authentication challenge.



## -syntax

````
typedef struct _WWAN_AUTH_SIM_RESPONSE {
  BYTE  Sres1[WWAN_AUTH_SRES_LEN];
  BYTE  Kc1[WWAN_AUTH_KC_LEN];
  BYTE  Sres2[WWAN_AUTH_SRES_LEN];
  BYTE  Kc2[WWAN_AUTH_KC_LEN];
  BYTE  Sres3[WWAN_AUTH_SRES_LEN];
  BYTE  Kc3[WWAN_AUTH_KC_LEN];
  ULONG n;
} WWAN_AUTH_SIM_RESPONSE, *PWWAN_AUTH_SIM_RESPONSE;
````


## -struct-fields

### -field Sres1[WWAN_AUTH_SRES_LEN]

Response 1 of 32 bit. This member represents a multi-byte value in little-endian format.


### -field Kc1[WWAN_AUTH_KC_LEN]

Encryption key 1 of 64 bit. This member represents a multi-byte value in little-endian format.


### -field Sres2[WWAN_AUTH_SRES_LEN]

Response 2 of 32 bit. This member represents a multi-byte value in little-endian format.


### -field Kc2[WWAN_AUTH_KC_LEN]

Encryption key 2 of 64 bit. This member represents a multi-byte value in little-endian format.


### -field Sres3[WWAN_AUTH_SRES_LEN]

Response 3 of 32 bit. This member represents a multi-byte value in little-endian format.


### -field Kc3[WWAN_AUTH_KC_LEN]

Encryption key 3 of 64 bit. This member represents a multi-byte value in little-endian format.


### -field n

The number of responses.


## -remarks
The <b>n</b> member can be either <b>2</b> or <b>3</b>, according to RFC 4186. If it is set to <b>2</b>, use the <b>Sres1</b>/<b>Kc1</b> and <b>Sres2</b>/<b>Kc2</b> members. If it is set to <b>3</b>,use <b>Sres1</b>/<b>Kc1</b>, <b>Sres2</b>/<b>Kc2</b>, and <b>Sres3</b>/<b>Kc3</b> members.

The <a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a> structure uses this structure.


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_SIM_RESPONSE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

