---
UID: NS:wlanihvtypes._DOT11EXT_IHV_PARAMS
title: "_DOT11EXT_IHV_PARAMS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_params.htm
old-project: netvista
ms.assetid: 1264bfe7-3ab6-4ba0-aa41-cf81bc9bb687
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_DOT11EXT_IHV_PARAMS, Native_802.11_data_types_90966964-74cc-4ff7-ae77-2807ab20d869.xml, PDOT11EXT_IHV_PARAMS structure pointer [Network Drivers Starting with Windows Vista], DOT11EXT_IHV_PARAMS structure [Network Drivers Starting with Windows Vista], *PDOT11EXT_IHV_PARAMS, netvista.dot11ext_ihv_params, DOT11EXT_IHV_PARAMS, PDOT11EXT_IHV_PARAMS, wlanihvtypes/DOT11EXT_IHV_PARAMS, wlanihvtypes/PDOT11EXT_IHV_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihvtypes.h
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
-	wlanihvtypes.h
apiname:
-	DOT11EXT_IHV_PARAMS
product: Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_PARAMS, *PDOT11EXT_IHV_PARAMS
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_PARAMS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_PARAMS structure defines the parameters associated with an IHV profile.


## -syntax


````
typedef struct _DOT11EXT_IHV_PARAMS {
  DOT11EXT_IHV_PROFILE_PARAMS dot11ExtIhvProfileParams;
  WCHAR                       wstrProfileName[MS_MAX_PROFILE_NAME_LENGTH];
  DWORD                       dwProfileTypeFlags;
  GUID                        interfaceGuid;
} DOT11EXT_IHV_PARAMS, *PDOT11EXT_IHV_PARAMS;
````


## -struct-fields




### -field dot11ExtIhvProfileParams

A 
     <a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">
     DOT11EXT_IHV_PROFILE_PARAMS</a> structure that specifies general parameters of a basic service set
     (BSS) network with which a network profile will be applied.


### -field wstrProfileName

A string that defines the IHV profile name.


### -field dwProfileTypeFlags

The flags associated with this IHV profile type.


### -field interfaceGuid

The globally unique identifier (GUID) for the wireless LAN (WLAN) adapter. 
     

The operating system passes the GUID and other data related to the WLAN adapter through the 
     <i>pDot11Adapter</i> parameter of the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">
     Dot11ExtIhvInitAdapter</a> function, which the operating system calls when it detects the arrival of
     the WLAN adapter. For more information about this operation, see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff557044">802.11 WLAN Adapter
     Arrival</a>.


## -see-also

<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_PARAMS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

