---
UID: NE:wwan._WWAN_CONTEXT_TYPE
title: "_WWAN_CONTEXT_TYPE"
author: windows-driver-content
description: The WWAN_CONTEXT_TYPE enumeration lists the different types of connection contexts that are supported by the MB device.
old-location: netvista\wwan_context_type.htm
old-project: netvista
ms.assetid: 73a18050-fc89-41df-82ce-0f29c5716496
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WwanContextTypeNone, WwanContextTypeVpn, *PWWAN_CONTEXT_TYPE, netvista.wwan_context_type, WwanRef_2f94e3ef-ec5c-47cc-8fe0-295c517ad43a.xml, WwanContextTypeVideoShare, wwan/WwanContextTypeCustom, WWAN_CONTEXT_TYPE enumeration [Network Drivers Starting with Windows Vista], wwan/WwanContextTypeVideoShare, wwan/WwanContextTypeMax, wwan/WwanContextTypeInternet, PWWAN_CONTEXT_TYPE, WWAN_CONTEXT_TYPE, WwanContextTypePurchase, PWWAN_CONTEXT_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], wwan/WwanContextTypePurchase, wwan/PWWAN_CONTEXT_TYPE, WwanContextTypeInternet, WwanContextTypeVoice, wwan/WWAN_CONTEXT_TYPE, wwan/WwanContextTypeNone, wwan/WwanContextTypeVpn, WwanContextTypeMax, _WWAN_CONTEXT_TYPE, wwan/WwanContextTypeVoice, WwanContextTypeCustom
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
-	WWAN_CONTEXT_TYPE
product: Windows
targetos: Windows
req.typenames: WWAN_CONTEXT_TYPE, *PWWAN_CONTEXT_TYPE
req.product: Windows 10 or later.
---

# _WWAN_CONTEXT_TYPE enumeration


## -description


The WWAN_CONTEXT_TYPE enumeration lists the different types of connection contexts that are supported
  by the MB device.


## -syntax


````
typedef enum _WWAN_CONTEXT_TYPE { 
  WwanContextTypeNone        = 0,
  WwanContextTypeInternet,
  WwanContextTypeVpn,
  WwanContextTypeVoice,
  WwanContextTypeVideoShare,
  WwanContextTypeCustom,
  WwanContextTypePurchase,
  WwanContextTypeMax
} WWAN_CONTEXT_TYPE, *PWWAN_CONTEXT_TYPE;
````


## -enum-fields




### -field WwanContextTypeNone

The context is not yet provisioned.


### -field WwanContextTypeInternet

The context represents a connection to the Internet.


### -field WwanContextTypeVpn

The context represents a connection to virtual private network (VPN to a corporate
     network).


### -field WwanContextTypeVoice

The context represents a connection to a Voice-over-IP (VOIP) service.


### -field WwanContextTypeVideoShare

The context represents a connection to a video sharing service.


### -field WwanContextTypeCustom

The context represents a connection to a custom service.


### -field WwanContextTypePurchase

Purchase a connection. For example, a walled garden, hot-lining or captive portal.


### -field WwanContextTypeMms


### -field WwanContextTypeIms


### -field WwanContextTypeAdmin


### -field WwanContextTypeApp


### -field WwanContextTypeXcap


### -field WwanContextTypeTethering


### -field WwanContextTypeEmergencyCall


### -field WwanContextTypeLteAttach


### -field WwanContextTypeMax

The total number of supported context types.


## -remarks



This enumeration indicates the usage of the provisioned context. For example, whether the context is
    used to connect to the Internet, or to a VPN into a corporate network. Miniport driver should specify 
    <b>WwanContextTypeNone</b> for empty (unprovisioned) context slots.




## -see-also

<a href="..\wwan\ns-wwan-_wwan_context.md">WWAN_CONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_CONTEXT_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

