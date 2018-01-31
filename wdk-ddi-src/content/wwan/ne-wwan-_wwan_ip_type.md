---
UID: NE:wwan._WWAN_IP_TYPE
title: "_WWAN_IP_TYPE"
author: windows-driver-content
description: The WWAN_IP_TYPE enumeration lists the different levels of supported IP.
old-location: netvista\wwan_ip_type.htm
old-project: netvista
ms.assetid: E4CE7BE7-021A-4C9A-B467-B63AACEC1266
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_WWAN_IP_TYPE, WWAN_IP_TYPE enumeration [Network Drivers Starting with Windows Vista], wwan/WWAN_IP_TYPE, WwanIPTypeIpv4v6, wwan/WwanIPTypeIpv4v6, netvista.wwan_ip_type, wwan/WwanIPTypeDefault, WwanIPTypeIPv4, wwan/WwanIPTypeIPv4, WwanIPTypeDefault, *PWWAN_IP_TYPE, WwanIPTypeIPv6, wwan/WwanIPTypeIPv6, WWAN_IP_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
-	WWAN_IP_TYPE
product: Windows
targetos: Windows
req.typenames: WWAN_IP_TYPE, *PWWAN_IP_TYPE
req.product: Windows 10 or later.
---

# _WWAN_IP_TYPE enumeration


## -description


The WWAN_IP_TYPE enumeration lists the different levels of supported IP.


## -syntax


````
typedef enum _WWAN_IP_TYPE { 
  WwanIPTypeDefault  = 0,
  WwanIPTypeIPv4     = ,
  WwanIPTypeIPv6     = ,
  WwanIPTypeIpv4v6   = 
} WWAN_IP_TYPE;
````


## -enum-fields




#### - WwanIPTypeDefault

Default IP.


#### - WwanIPTypeIPv4

IPv4.


#### - WwanIPTypeIPv6

IPv6


#### - WwanIPTypeIpv4v6

IPv4 with IPv6


### -field WwanIPTypeXlat




## -see-also

<a href="..\wwan\ns-wwan-_wwan_set_context_state.md">WWAN_SET_CONTEXT_STATE</a>

<a href="..\wwan\ns-wwan-_wwan_context_state.md">WWAN_CONTEXT_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_IP_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

