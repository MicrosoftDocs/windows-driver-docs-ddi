---
UID: NS:wwan._WWAN_AUTH_CHALLENGE
title: "_WWAN_AUTH_CHALLENGE"
author: windows-driver-content
description: The WWAN_AUTH_CHALLENGE structure represents an authentication challenge for a specific method.
old-location: netvista\wwan_auth_challenge.htm
old-project: netvista
ms.assetid: A31B9E91-B5F9-4EF3-AD9E-A5E26CBD4B35
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWWAN_AUTH_CHALLENGE, PWWAN_AUTH_CHALLENGE, PWWAN_AUTH_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_CHALLENGE, WWAN_AUTH_CHALLENGE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_CHALLENGE, netvista.wwan_auth_challenge, wwan/PWWAN_AUTH_CHALLENGE, wwan/WWAN_AUTH_CHALLENGE"
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
-	WWAN_AUTH_CHALLENGE
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_CHALLENGE, *PWWAN_AUTH_CHALLENGE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_CHALLENGE structure


## -description


The WWAN_AUTH_CHALLENGE structure represents an authentication challenge for a specific method.


## -syntax


````
typedef struct _WWAN_AUTH_CHALLENGE {
  WWAN_AUTH_METHOD AuthMethod;
  union {
    WWAN_AUTH_SIM_CHALLENGE  AuthSim;
    WWAN_AUTH_AKA_CHALLENGE  AuthAka;
    WWAN_AUTH_AKAP_CHALLENGE AuthAkap;
  } u;
} WWAN_AUTH_CHALLENGE, *PWWAN_AUTH_CHALLENGE;
````


## -struct-fields




### -field AuthMethod

The authentication challenge method.


### -field u

The container union for the different authentication challenge methods.



#### AuthSim

The challenge that uses the SIM authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthSim</i>, use this member.



#### AuthAka

The challenge that uses the AKA authentication method.  If <b>AuthMethod</b> is set to <i>WwanAuthAka</i>, use this member.



#### AuthAkap

The challenge that uses the AKA' authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthAkap,</i> use this member.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_auth_sim_challenge.md">WWAN_AUTH_SIM_CHALLENGE</a>



<a href="..\wwan\ns-wwan-_wwan_auth_aka_challenge.md">WWAN_AUTH_AKA_CHALLENGE</a>



<a href="..\wwan\ns-wwan-_wwan_auth_akap_challenge.md">WWAN_AUTH_AKAP_CHALLENGE</a>



<a href="..\wwan\ne-wwan-_wwan_auth_method.md">WWAN_AUTH_METHOD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_CHALLENGE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

