---
UID: NC:wlanihv.DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES
title: DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetvirtualstationapproperties.htm
old-project: netvista
ms.assetid: 11ba5799-2bb5-475f-bf69-cf1a1c3c128c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extsetvirtualstationapproperties, Dot11ExtSetVirtualStationAPProperties callback function [Network Drivers Starting with Windows Vista], Dot11ExtSetVirtualStationAPProperties, DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES, DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES, wlanihv/Dot11ExtSetVirtualStationAPProperties, Native_802.11_IHV_Ext_99551e02-eec3-413e-a14d-60d6ce5c09ee.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
-	UserDefined
apilocation:
-	wlanihv.h
apiname:
-	Dot11ExtSetVirtualStationAPProperties
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetVirtualStationAPProperties</b> function to specify the current IHV
  profile connection.


## -prototype


````
DWORD WINAPI * Dot11ExtSetVirtualStationAPProperties(
  _In_opt_   HANDLE                                hDot11SvcHandle,
  _In_opt_   HANDLE                                hConnectSession,
  _In_       DWORD                                 dwNumProperties,
  _In_       PDOT11EXT_VIRTUAL_STATION_AP_PROPERTY pProperties,
  _Reserved_ LPVOID                                pvReserved
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

An optional handle used by the operating system to reference the primary physical wireless LAN
     (WLAN) adapter. This handle value was received as the 
     <i>hDot11SvcHandle</i> parameter through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param hConnectSession [in, optional]

The handle used by the operating system to reference the current connection session with the basic
     service set (BSS) network. This handle value was received as the 
     <i>hConnectSession</i> parameter through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.


### -param dwNumProperties [in]

The number of elements in the array of structures pointed to by the 
     <i>pProperties</i> parameter.


### -param pProperties [in]

A pointer to an array of 
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_virtual_station_ap_property.md">
     DOT11EXT_VIRTUAL_STATION_AP_PROPERTY</a> structures that specify the properties of access points (APs)
     that the virtual 802.11 station is attempting to host in the current connection session.


### -param pvReserved

This parameter is reserved for use by the operating system and should be <b>NULL</b>.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.




## -remarks



If the current IHV profile connection is an access point (AP), and the IHV Extensions DLL can provide
    to the operating system the settings used by the AP, the operating system can provide additional
    information to users who request AP-related service from the operating system.

If the IHV Extensions DLL calls 
    <b>Dot11ExtSetVirtualStationAPProperties</b>, it must do so before it calls the
    
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
    Dot11ExtIhvPerformPreAssociate</a> IHV Handler function. If 
    <b>Dot11ExtSetVirtualStationAPProperties</b> is not called before successful
    completion of the pre-association operation, the operating system makes no assumptions about the nature
    of the IHV profile.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_virtual_station_ap_property.md">
   DOT11EXT_VIRTUAL_STATION_AP_PROPERTY</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

