---
UID: NS:wlanihv._DOT11EXT_IHV_CONNECTIVITY_PROFILE
title: _DOT11EXT_IHV_CONNECTIVITY_PROFILE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_connectivity_profile.htm
old-project: netvista
ms.assetid: 56ef9b59-5dbb-4720-bae1-7af6d9dbc110
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11EXT_IHV_CONNECTIVITY_PROFILE, *PDOT11EXT_IHV_CONNECTIVITY_PROFILE, DOT11EXT_IHV_CONNECTIVITY_PROFILE
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
req.alt-api: DOT11EXT_IHV_CONNECTIVITY_PROFILE
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
req.typenames: *PDOT11EXT_IHV_CONNECTIVITY_PROFILE, DOT11EXT_IHV_CONNECTIVITY_PROFILE
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_CONNECTIVITY_PROFILE structure



## -description

## -syntax

````
typedef struct _DOT11EXT_IHV_CONNECTIVITY_PROFILE {
  LPWSTR pszXmlFragmentIhvConnectivity;
} DOT11EXT_IHV_CONNECTIVITY_PROFILE, *PDOT11EXT_IHV_CONNECTIVITY_PROFILE;
````


## -struct-fields

### -field pszXmlFragmentIhvConnectivity

A pointer to the string that defines the IHV connectivity profile.


## -remarks
