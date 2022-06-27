---
UID: NS:wwan._WWAN_AUTH_SIM_RESPONSE
title: _WWAN_AUTH_SIM_RESPONSE (wwan.h)
description: The WWAN_AUTH_SIM_RESPONSE structure represents a response to a SIM authentication challenge.
old-location: netvista\wwan_auth_sim_response.htm
tech.root: netvista
ms.date: 03/11/2022
keywords: ["WWAN_AUTH_SIM_RESPONSE structure"]
ms.keywords: "*PWWAN_AUTH_SIM_RESPONSE, PWWAN_AUTH_SIM_RESPONSE, PWWAN_AUTH_SIM_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_SIM_RESPONSE, WWAN_AUTH_SIM_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_SIM_RESPONSE, netvista.wwan_auth_sim_response, wwan/PWWAN_AUTH_SIM_RESPONSE, wwan/WWAN_AUTH_SIM_RESPONSE"
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
targetos: Windows
req.typenames: WWAN_AUTH_SIM_RESPONSE, *PWWAN_AUTH_SIM_RESPONSE
f1_keywords:
 - _WWAN_AUTH_SIM_RESPONSE
 - wwan/_WWAN_AUTH_SIM_RESPONSE
 - PWWAN_AUTH_SIM_RESPONSE
 - wwan/PWWAN_AUTH_SIM_RESPONSE
 - WWAN_AUTH_SIM_RESPONSE
 - wwan/WWAN_AUTH_SIM_RESPONSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_AUTH_SIM_RESPONSE
 - PWWAN_AUTH_SIM_RESPONSE
 - WWAN_AUTH_SIM_RESPONSE
---

# _WWAN_AUTH_SIM_RESPONSE structure


## -description

The WWAN_AUTH_SIM_RESPONSE structure represents a response to a SIM authentication challenge.

## -struct-fields



### -field n

The number of responses.


### -field Kc1

Encryption key 1 of 64 bit. This member represents a multi-byte value in little-endian format.


### -field Kc2

Encryption key 2 of 64 bit. This member represents a multi-byte value in little-endian format.


### -field Kc3

Encryption key 3 of 64 bit. This member represents a multi-byte value in little-endian format.


### -field Sres1

Response 1 of 32 bit. This member represents a multi-byte value in little-endian format.


### -field Sres2

Response 2 of 32 bit. This member represents a multi-byte value in little-endian format.


### -field Sres3

Response 3 of 32 bit. This member represents a multi-byte value in little-endian format.

## -remarks

The <b>n</b> member can be either <b>2</b> or <b>3</b>, according to RFC 4186. If it is set to <b>2</b>, use the <b>Sres1</b>/<b>Kc1</b> and <b>Sres2</b>/<b>Kc2</b> members. If it is set to <b>3</b>,use <b>Sres1</b>/<b>Kc1</b>, <b>Sres2</b>/<b>Kc2</b>, and <b>Sres3</b>/<b>Kc3</b> members.

The <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_response">WWAN_AUTH_RESPONSE</a> structure uses this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_response">WWAN_AUTH_RESPONSE</a>

