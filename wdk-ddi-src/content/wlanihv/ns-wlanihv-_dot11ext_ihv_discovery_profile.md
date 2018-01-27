---
UID: NS:wlanihv._DOT11EXT_IHV_DISCOVERY_PROFILE
title: _DOT11EXT_IHV_DISCOVERY_PROFILE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_discovery_profile.htm
old-project: netvista
ms.assetid: 9044d045-a997-4660-815d-07dad0ac832e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PDOT11EXT_IHV_DISCOVERY_PROFILE structure pointer [Network Drivers Starting with Windows Vista], DOT11EXT_IHV_DISCOVERY_PROFILE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_38fefdc4-fa98-4986-822b-807caa03b205.xml, wlanihv/PDOT11EXT_IHV_DISCOVERY_PROFILE, DOT11EXT_IHV_DISCOVERY_PROFILE, _DOT11EXT_IHV_DISCOVERY_PROFILE, wlanihv/DOT11EXT_IHV_DISCOVERY_PROFILE, netvista.dot11ext_ihv_discovery_profile, *PDOT11EXT_IHV_DISCOVERY_PROFILE, PDOT11EXT_IHV_DISCOVERY_PROFILE
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
-	DOT11EXT_IHV_DISCOVERY_PROFILE
product: Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_DISCOVERY_PROFILE, *PDOT11EXT_IHV_DISCOVERY_PROFILE
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_DISCOVERY_PROFILE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_DISCOVERY_PROFILE structure specifies a single IHV discovery profile.


## -syntax


````
typedef struct _DOT11EXT_IHV_DISCOVERY_PROFILE {
  DOT11EXT_IHV_CONNECTIVITY_PROFILE IhvConnectivityProfile;
  DOT11EXT_IHV_SECURITY_PROFILE     IhvSecurityProfile;
} DOT11EXT_IHV_DISCOVERY_PROFILE, *PDOT11EXT_IHV_DISCOVERY_PROFILE;
````


## -struct-fields




### -field IhvConnectivityProfile

The IHV connectivity profile specified by a 
     <mshelp:link keywords="netvista.dot11ext_ihv_connectivity_profile" tabindex="0"><b>
     DOT11EXT_IHV_CONNECTIVITY_PROFILE</b></mshelp:link> structure.


### -field IhvSecurityProfile

The IHV security profile specified by a 
     <mshelp:link keywords="netvista.dot11ext_ihv_security_profile" tabindex="0"><b>
     DOT11EXT_IHV_SECURITY_PROFILE</b></mshelp:link> structure.


## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_security_profile.md">DOT11EXT_IHV_SECURITY_PROFILE</a>

<mshelp:link keywords="netvista.dot11ext_ihv_connectivity_profile" tabindex="0"><b>
   DOT11EXT_IHV_CONNECTIVITY_PROFILE</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_DISCOVERY_PROFILE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

