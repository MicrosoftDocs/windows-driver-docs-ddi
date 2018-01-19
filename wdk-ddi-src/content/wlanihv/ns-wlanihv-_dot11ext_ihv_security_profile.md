---
UID: NS:wlanihv._DOT11EXT_IHV_SECURITY_PROFILE
title: _DOT11EXT_IHV_SECURITY_PROFILE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_security_profile.htm
old-project: netvista
ms.assetid: cbfeace3-6492-4011-9ca8-c40ba4f47d22
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11EXT_IHV_SECURITY_PROFILE, DOT11EXT_IHV_SECURITY_PROFILE, *PDOT11EXT_IHV_SECURITY_PROFILE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11EXT_IHV_SECURITY_PROFILE
req.alt-loc: wlanihv.h
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
req.typenames: DOT11EXT_IHV_SECURITY_PROFILE, *PDOT11EXT_IHV_SECURITY_PROFILE
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_SECURITY_PROFILE structure



## -description

## -syntax

````
typedef struct _DOT11EXT_IHV_SECURITY_PROFILE {
  LPWSTR pszXmlFragmentIhvSecurity;
  BOOL   bUseMSOnex;
} DOT11EXT_IHV_SECURITY_PROFILE, *PDOT11EXT_IHV_SECURITY_PROFILE;
````


## -struct-fields

### -field pszXmlFragmentIhvSecurity

A pointer to the string that defines the IHV security profile.


### -field bUseMSOnex

A flag that indicates whether the IHV security profile is using the Microsoft 802.1X
     implementation. If <b>TRUE</b>, the profile uses the Microsoft 802.1X implementation.


## -remarks
