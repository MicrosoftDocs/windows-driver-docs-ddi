---
UID: NS:wwan._WWAN_AUTH_SIM_RESPONSE
title: _WWAN_AUTH_SIM_RESPONSE (wwan.h)
description: The WWAN_AUTH_SIM_RESPONSE structure represents a response to a SIM authentication challenge.
old-location: netvista\wwan_auth_sim_response.htm
tech.root: netvista
ms.assetid: C259CA95-D119-47EB-A32D-9C9E284B6CD4
ms.date: 05/02/2018
keywords: ["_WWAN_AUTH_SIM_RESPONSE structure"]
ms.keywords: "*PWWAN_AUTH_SIM_RESPONSE, PWWAN_AUTH_SIM_RESPONSE, PWWAN_AUTH_SIM_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_SIM_RESPONSE, WWAN_AUTH_SIM_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_SIM_RESPONSE, netvista.wwan_auth_sim_response, wwan/PWWAN_AUTH_SIM_RESPONSE, wwan/WWAN_AUTH_SIM_RESPONSE"
f1_keywords:
 - "wwan/WWAN_AUTH_SIM_RESPONSE"
 - "WWAN_AUTH_SIM_RESPONSE"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
- wwan.h
api_name:
- WWAN_AUTH_SIM_RESPONSE
targetos: Windows
req.typenames: WWAN_AUTH_SIM_RESPONSE, *PWWAN_AUTH_SIM_RESPONSE
---

# _WWAN_AUTH_SIM_RESPONSE structure


## -description


The WWAN_AUTH_SIM_RESPONSE structure represents a response to a SIM authentication challenge.


## -struct-fields




### -field Sres1

 


### -field Kc1

 


### -field Sres2

 


### -field Kc2

 


### -field Sres3

 


### -field Kc3

 


### -field n

The number of responses.


#### - Kc1[WWAN_AUTH_KC_LEN]

Encryption key 1 of 64 bit. This member represents a multi-byte value in little-endian format.


#### - Kc2[WWAN_AUTH_KC_LEN]

Encryption key 2 of 64 bit. This member represents a multi-byte value in little-endian format.


#### - Kc3[WWAN_AUTH_KC_LEN]

Encryption key 3 of 64 bit. This member represents a multi-byte value in little-endian format.


#### - Sres1[WWAN_AUTH_SRES_LEN]

Response 1 of 32 bit. This member represents a multi-byte value in little-endian format.


#### - Sres2[WWAN_AUTH_SRES_LEN]

Response 2 of 32 bit. This member represents a multi-byte value in little-endian format.


#### - Sres3[WWAN_AUTH_SRES_LEN]

Response 3 of 32 bit. This member represents a multi-byte value in little-endian format.


## -remarks



The <b>n</b> member can be either <b>2</b> or <b>3</b>, according to RFC 4186. If it is set to <b>2</b>, use the <b>Sres1</b>/<b>Kc1</b> and <b>Sres2</b>/<b>Kc2</b> members. If it is set to <b>3</b>,use <b>Sres1</b>/<b>Kc1</b>, <b>Sres2</b>/<b>Kc2</b>, and <b>Sres3</b>/<b>Kc3</b> members.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_response">WWAN_AUTH_RESPONSE</a> structure uses this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_response">WWAN_AUTH_RESPONSE</a>
 

 

