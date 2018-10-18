---
UID: NE:wwan._WWAN_CONTEXT_TYPE
title: "_WWAN_CONTEXT_TYPE"
author: windows-driver-content
description: The WWAN_CONTEXT_TYPE enumeration lists the different types of connection contexts that are supported by the MB device.
old-location: netvista\wwan_context_type.htm
tech.root: netvista
ms.assetid: 73a18050-fc89-41df-82ce-0f29c5716496
ms.date: 5/2/2018
ms.keywords: "*PWWAN_CONTEXT_TYPE, PWWAN_CONTEXT_TYPE, PWWAN_CONTEXT_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_CONTEXT_TYPE, WWAN_CONTEXT_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanContextTypeCustom, WwanContextTypeInternet, WwanContextTypeMax, WwanContextTypeNone, WwanContextTypePurchase, WwanContextTypeVideoShare, WwanContextTypeVoice, WwanContextTypeVpn, WwanRef_2f94e3ef-ec5c-47cc-8fe0-295c517ad43a.xml, _WWAN_CONTEXT_TYPE, netvista.wwan_context_type, wwan/PWWAN_CONTEXT_TYPE, wwan/WWAN_CONTEXT_TYPE, wwan/WwanContextTypeCustom, wwan/WwanContextTypeInternet, wwan/WwanContextTypeMax, wwan/WwanContextTypeNone, wwan/WwanContextTypePurchase, wwan/WwanContextTypeVideoShare, wwan/WwanContextTypeVoice, wwan/WwanContextTypeVpn"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_CONTEXT_TYPE
product:
- Windows
targetos: Windows
req.typenames: WWAN_CONTEXT_TYPE, *PWWAN_CONTEXT_TYPE
---

# _WWAN_CONTEXT_TYPE enumeration


## -description


The WWAN_CONTEXT_TYPE enumeration lists the different types of connection contexts that are supported
  by the MB device.


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

The context represents a connection for a multimedia message (MMS).

### -field WwanContextTypeIms

The context represents a connection for IP Multimedia Subsystem (IMS).

### -field WwanContextTypeAdmin

The context is used for administrative purposes such as device management.

### -field WwanContextTypeApp

The context represents a connection for certain applications whitelisted by mobile operators.

### -field WwanContextTypeXcap

The context is used for XCAP provisioning on IMS services.

### -field WwanContextTypeTethering

The context is used for mobile hotspot tethering.

### -field WwanContextTypeEmergencyCall

The context is used for IMS emergency calling.

### -field WwanContextTypeLteAttach

The context represents an attachment to LTE.

### -field WwanContextTypeMax

The total number of supported context types.

## -remarks



This enumeration indicates the usage of the provisioned context. For example, whether the context is
    used to connect to the Internet, or to a VPN into a corporate network. Miniport drivers should specify 
    <b>WwanContextTypeNone</b> for empty (unprovisioned) context slots.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571201">WWAN_CONTEXT</a>
 

 

