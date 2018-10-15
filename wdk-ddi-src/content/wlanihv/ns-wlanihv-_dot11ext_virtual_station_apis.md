---
UID: NS:wlanihv._DOT11EXT_VIRTUAL_STATION_APIS
title: "_DOT11EXT_VIRTUAL_STATION_APIS"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_virtual_station_apis.htm
tech.root: netvista
ms.assetid: 5487375a-7d50-4ddd-a666-8727f45b85dc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11EXT_VIRTUAL_STATION_APIS, DOT11EXT_VIRTUAL_STATION_APIS, DOT11EXT_VIRTUAL_STATION_APIS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_0b2dadd3-7d60-4836-9171-c2c11b56010d.xml, PDOT11EXT_VIRTUAL_STATION_APIS, PDOT11EXT_VIRTUAL_STATION_APIS structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_VIRTUAL_STATION_APIS, netvista.dot11ext_virtual_station_apis, wlanihv/DOT11EXT_VIRTUAL_STATION_APIS, wlanihv/PDOT11EXT_VIRTUAL_STATION_APIS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wlanihv.h
api_name:
-	DOT11EXT_VIRTUAL_STATION_APIS
product:
- Windows
targetos: Windows
req.typenames: DOT11EXT_VIRTUAL_STATION_APIS, *PDOT11EXT_VIRTUAL_STATION_APIS
req.product: Windows 10 or later.
---

# _DOT11EXT_VIRTUAL_STATION_APIS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_VIRTUAL_STATION_APIS structure specifies a list of pointers to the IHV Extensibility
  virtual station functions that are supported by the operating system.


## -syntax


```
typedef struct _DOT11EXT_VIRTUAL_STATION_APIS {
  DOT11EXT_REQUEST_VIRTUAL_STATION           Dot11ExtRequestVirtualStation;
  DOT11EXT_RELEASE_VIRTUAL_STATION           Dot11ExtReleaseVirtualStation;
  DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES  Dot11ExtQueryVirtualStationProperties;
  DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES Dot11ExtSetVirtualStationAPProperties;
} DOT11EXT_VIRTUAL_STATION_APIS, *PDOT11EXT_VIRTUAL_STATION_APIS;
```


## -struct-fields




### -field Dot11ExtRequestVirtualStation

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_request_virtual_station.md">
     Dot11ExtRequestVirtualStation</a> function.


### -field Dot11ExtReleaseVirtualStation

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_release_virtual_station.md">
     Dot11ExtReleaseVirtualStation</a> function.


### -field Dot11ExtQueryVirtualStationProperties

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_query_virtual_station_properties.md">
     Dot11ExtQueryVirtualStationProperties</a> function.


### -field Dot11ExtSetVirtualStationAPProperties

A pointer to the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_set_virtual_station_ap_properties.md">
     Dot11ExtSetVirtualStationAPProperties</a> function.


## -remarks



The IHV Extensibility virtual station functions are not statically or dynamically linked to the IHV
    Extensions DLL. Instead, when the operating system calls the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_virtual_station.md">
    Dot11ExtIhvInitVirtualStation</a> IHV handler function, it passes the list of pointers to the IHV
    Extensibility functions through the
    <i>pDot11ExtVSAPI</i> parameter.

<div class="alert"><b>Note</b>  The IHV Extensions DLL is allowed to call the virtual station API functions that
    the
    <i>pDot11ExtVSAPI</i> parameter points to only after the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_virtual_station.md">
    Dot11ExtIhvInitVirtualStation</a> function returns.</div>
<div> </div>
All of the function pointers are required and must not be set to <b>NULL</b>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_virtual_station_ap_properties.md">
   Dot11ExtSetVirtualStationAPProperties</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_release_virtual_station.md">
   Dot11ExtReleaseVirtualStation</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_request_virtual_station.md">
   Dot11ExtRequestVirtualStation</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_virtual_station.md">
   Dot11ExtIhvInitVirtualStation</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_query_virtual_station_properties.md">
   Dot11ExtQueryVirtualStationProperties</a>



 

 


