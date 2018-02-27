---
UID: NS:wlanihv._DOT11EXT_IHV_DISCOVERY_PROFILE_LIST
title: "_DOT11EXT_IHV_DISCOVERY_PROFILE_LIST"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_discovery_profile_list.htm
old-project: netvista
ms.assetid: 8fa104bd-b594-4909-bb49-0c9d013b1696
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST, DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, DOT11EXT_IHV_DISCOVERY_PROFILE_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_824a6794-5502-459a-9a47-409d51a6871a.xml, PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST, PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, netvista.dot11ext_ihv_discovery_profile_list, wlanihv/DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, wlanihv/PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST"
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
-	wlanihv.h
apiname:
-	DOT11EXT_IHV_DISCOVERY_PROFILE_LIST
product: Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_DISCOVERY_PROFILE_LIST, *PDOT11EXT_IHV_DISCOVERY_PROFILE_LIST
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_DISCOVERY_PROFILE_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_DISCOVERY_PROFILE_LIST structure specifies a list of IHV discovery profiles.


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


## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_discovery_profile.md">
   DOT11EXT_IHV_DISCOVERY_PROFILE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_DISCOVERY_PROFILE_LIST structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

