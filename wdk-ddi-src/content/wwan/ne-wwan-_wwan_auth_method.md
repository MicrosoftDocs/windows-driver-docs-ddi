---
UID: NE:wwan._WWAN_AUTH_METHOD
title: "_WWAN_AUTH_METHOD"
author: windows-driver-content
description: The WWAN_AUTH_METHOD enumeration lists supported authentication methods.
old-location: netvista\wwan_auth_method.htm
old-project: netvista
ms.assetid: D24D8C90-8F65-42BC-8FBC-308ECC4A73C9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_AUTH_METHOD, WWAN_AUTH_METHOD, WWAN_AUTH_METHOD enumeration [Network Drivers Starting with Windows Vista], WwanAuthAka, WwanAuthAkaPrime, WwanAuthMethodMax, WwanAuthSim, _WWAN_AUTH_METHOD, netvista.wwan_auth_method, wwan/WWAN_AUTH_METHOD, wwan/WwanAuthAka, wwan/WwanAuthAkaPrime, wwan/WwanAuthMethodMax, wwan/WwanAuthSim"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
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
-	WWAN_AUTH_METHOD
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_METHOD, *PWWAN_AUTH_METHOD
req.product: Windows 10 or later.
---

# _WWAN_AUTH_METHOD enumeration


## -description


The WWAN_AUTH_METHOD enumeration lists supported authentication methods.


## -syntax


````
typedef enum _WWAN_AUTH_METHOD { 
  WwanAuthSim        = 0,
  WwanAuthAka,
  WwanAuthAkaPrime,
  WwanAuthMethodMax
} WWAN_AUTH_METHOD;
````


## -enum-fields




### -field WwanAuthSim

Authenticate using the SIM method.


### -field WwanAuthAka

Authenticate using the AKA method.


### -field WwanAuthAkaPrime

Authenticate using the AKA' (AKA Prime) method.


### -field WwanAuthMethodMax

This value is reserved. Do not use.


## -remarks



The <a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a> and <a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a> structures use this enumeration.




## -see-also

<a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a>



<a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a>



 

 


