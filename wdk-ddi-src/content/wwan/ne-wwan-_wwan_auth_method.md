---
UID: NE:wwan._WWAN_AUTH_METHOD
title: "_WWAN_AUTH_METHOD"
author: windows-driver-content
description: The WWAN_AUTH_METHOD enumeration lists supported authentication methods.
old-location: netvista\wwan_auth_method.htm
old-project: netvista
ms.assetid: D24D8C90-8F65-42BC-8FBC-308ECC4A73C9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PWWAN_AUTH_METHOD, ,, A, D, E, H, M, N, O, P, T, U, W, WWAN_AUTH_METHOD, WWAN_AUTH_METHOD enumeration [Network Drivers Starting with Windows Vista], WwanAuthAka, WwanAuthAkaPrime, WwanAuthMethodMax, WwanAuthSim, _, _WWAN_AUTH_METHOD, netvista.wwan_auth_method, wwan/WWAN_AUTH_METHOD, wwan/WwanAuthAka, wwan/WwanAuthAkaPrime, wwan/WwanAuthMethodMax, wwan/WwanAuthSim"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_METHOD enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

