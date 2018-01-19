---
UID: NS:wlanihv._DOT11EXT_IHV_DISCOVERY_PROFILE_LIST
title: _DOT11EXT_IHV_DISCOVERY_PROFILE_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_discovery_profile_list.htm
old-project: netvista
ms.assetid: 8fa104bd-b594-4909-bb49-0c9d013b1696
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, *PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST
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
req.alt-api: DOT11EXT_IHV_DISCOVERY_PROFILE_LIST
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
req.typenames: DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, *PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_DISCOVERY_PROFILE_LIST structure



## -description

## -syntax

````
typedef struct _DOT11EXT_IHV_DISCOVERY_PROFILE_LIST {
  DWORD                           dwCount;
  PDOT11EXT_IHV_DISCOVERY_PROFILE pIhvDiscoveryProfiles;
} DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, *PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST;
````


## -struct-fields

### -field dwCount

The number of 
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_discovery_profile.md">
     DOT11EXT_IHV_DISCOVERY_PROFILE</a> IHV discovery profiles.


### -field pIhvDiscoveryProfiles

A pointer to an array of 
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_discovery_profile.md">
     DOT11EXT_IHV_DISCOVERY_PROFILE</a> IHV discovery profiles.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_discovery_profile.md">
   DOT11EXT_IHV_DISCOVERY_PROFILE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_DISCOVERY_PROFILE_LIST structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

