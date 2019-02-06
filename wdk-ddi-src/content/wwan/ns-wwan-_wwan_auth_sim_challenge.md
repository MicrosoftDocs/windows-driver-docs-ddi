---
UID: NS:wwan._WWAN_AUTH_SIM_CHALLENGE
title: _WWAN_AUTH_SIM_CHALLENGE (wwan.h)
description: The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.
old-location: netvista\wwan_auth_sim_challenge.htm
tech.root: netvista
ms.assetid: E07F3ED0-2F20-40D9-AAAE-49C81168B998
ms.date: 05/02/2018
ms.keywords: "*PWWAN_AUTH_SIM_CHALLENGE, PWWAN_AUTH_SIM_CHALLENGE, PWWAN_AUTH_SIM_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_SIM_CHALLENGE, WWAN_AUTH_SIM_CHALLENGE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_SIM_CHALLENGE, netvista.wwan_auth_sim_challenge, wwan/PWWAN_AUTH_SIM_CHALLENGE, wwan/WWAN_AUTH_SIM_CHALLENGE"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_AUTH_SIM_CHALLENGE
product:
- Windows
targetos: Windows
req.typenames: WWAN_AUTH_SIM_CHALLENGE, *PWWAN_AUTH_SIM_CHALLENGE
---

# _WWAN_AUTH_SIM_CHALLENGE structure


## -description


The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.


## -struct-fields




### -field Rand1

 


### -field Rand2

 


### -field Rand3

 


### -field n

The number of random number challenges.


#### - Rand1[WWAN_AUTH_RAND_LEN]

The first 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


#### - Rand2[WWAN_AUTH_RAND_LEN]

The second 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


#### - Rand3[WWAN_AUTH_RAND_LEN]

The third 128-bit random number challenge value. This member represents a multi-byte value in little-endian format.


## -remarks



The <b>n</b> member can be either <b>2</b> or <b>3</b>, according to RFC 4186. If it is set to <b>2</b>, use the <b>Rand1</b> and <b>Rand2</b> members. If it is set to <b>3</b>, then the <b>Rand1</b>, <b>Rand2</b>, and <b>Rand3</b> members.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464127">WWAN_AUTH_CHALLENGE</a> structure uses this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464127">WWAN_AUTH_CHALLENGE</a>
 

 

