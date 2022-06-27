---
UID: NS:wwan._WWAN_AUTH_SIM_CHALLENGE
title: _WWAN_AUTH_SIM_CHALLENGE (wwan.h)
description: The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.
old-location: netvista\wwan_auth_sim_challenge.htm
tech.root: netvista
ms.date: 03/11/2022
keywords: ["WWAN_AUTH_SIM_CHALLENGE structure"]
ms.keywords: "*PWWAN_AUTH_SIM_CHALLENGE, PWWAN_AUTH_SIM_CHALLENGE, PWWAN_AUTH_SIM_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_SIM_CHALLENGE, WWAN_AUTH_SIM_CHALLENGE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_SIM_CHALLENGE, netvista.wwan_auth_sim_challenge, wwan/PWWAN_AUTH_SIM_CHALLENGE, wwan/WWAN_AUTH_SIM_CHALLENGE"
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
req.typenames: WWAN_AUTH_SIM_CHALLENGE, *PWWAN_AUTH_SIM_CHALLENGE
f1_keywords:
 - _WWAN_AUTH_SIM_CHALLENGE
 - wwan/_WWAN_AUTH_SIM_CHALLENGE
 - PWWAN_AUTH_SIM_CHALLENGE
 - wwan/PWWAN_AUTH_SIM_CHALLENGE
 - WWAN_AUTH_SIM_CHALLENGE
 - wwan/WWAN_AUTH_SIM_CHALLENGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_AUTH_SIM_CHALLENGE
 - PWWAN_AUTH_SIM_CHALLENGE
 - WWAN_AUTH_SIM_CHALLENGE
---

# _WWAN_AUTH_SIM_CHALLENGE structure


## -description

The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.

## -struct-fields

### -field n

The number of random number challenges.


### -field Rand1

The first 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


### -field Rand2

The second 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


### -field Rand3

The third 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.

## -remarks

The <b>n</b> member can be either <b>2</b> or <b>3</b>, according to RFC 4186. If it is set to <b>2</b>, use the <b>Rand1</b> and <b>Rand2</b> members. If it is set to <b>3</b>, then the <b>Rand1</b>, <b>Rand2</b>, and <b>Rand3</b> members.

The <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_challenge">WWAN_AUTH_CHALLENGE</a> structure uses this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_challenge">WWAN_AUTH_CHALLENGE</a>

