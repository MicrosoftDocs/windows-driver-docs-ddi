---
UID: NE:wwan._WWAN_AUTH_PROTOCOL
title: "_WWAN_AUTH_PROTOCOL"
author: windows-driver-content
description: The WWAN_AUTH_PROTOCOL enumeration lists the different types of authentication protocols that are supported by the MB device.
old-location: netvista\wwan_auth_protocol.htm
old-project: netvista
ms.assetid: 33c9523e-3195-456f-8e17-b9539475bc67
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_AUTH_PROTOCOL, PWWAN_AUTH_PROTOCOL, PWWAN_AUTH_PROTOCOL enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_PROTOCOL, WWAN_AUTH_PROTOCOL enumeration [Network Drivers Starting with Windows Vista], WwanAuthProtocolChap, WwanAuthProtocolMax, WwanAuthProtocolMsChapV2, WwanAuthProtocolNone, WwanAuthProtocolPap, WwanRef_b7f5b77c-f85f-4ed2-adfa-306b903da5fd.xml, _WWAN_AUTH_PROTOCOL, netvista.wwan_auth_protocol, wwan/PWWAN_AUTH_PROTOCOL, wwan/WWAN_AUTH_PROTOCOL, wwan/WwanAuthProtocolChap, wwan/WwanAuthProtocolMax, wwan/WwanAuthProtocolMsChapV2, wwan/WwanAuthProtocolNone, wwan/WwanAuthProtocolPap"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 7.
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
-	WWAN_AUTH_PROTOCOL
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_PROTOCOL, *PWWAN_AUTH_PROTOCOL
req.product: Windows 10 or later.
---

# _WWAN_AUTH_PROTOCOL enumeration


## -description


The WWAN_AUTH_PROTOCOL enumeration lists the different types of authentication protocols that are
  supported by the MB device.


## -enum-fields




### -field WwanAuthProtocolNone

No authentication protocol.


### -field WwanAuthProtocolPap

Unencrypted password authentication.


### -field WwanAuthProtocolChap

Use the Challenge Handshake Authentication Protocol (CHAP).


### -field WwanAuthProtocolMsChapV2

Use the Microsoft Challenge Handshake Authentication Protocol (CHAP) v2.0.


### -field WwanAuthProtocolAuto


### -field WwanAuthProtocolMax

The total number of supported authentication protocols.


## -remarks



This enumeration applies only to GSM devices. The MB Service specifies 
    <b>WwanAuthProtocolNone</b> as the authentication type for CDMA-based devices.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571201">WWAN_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571235">WWAN_SET_CONTEXT_STATE</a>
 

 

