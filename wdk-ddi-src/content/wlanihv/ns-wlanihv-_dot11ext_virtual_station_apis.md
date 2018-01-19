---
UID: NS:wlanihv._DOT11EXT_VIRTUAL_STATION_APIS
title: _DOT11EXT_VIRTUAL_STATION_APIS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_virtual_station_apis.htm
old-project: netvista
ms.assetid: 5487375a-7d50-4ddd-a666-8727f45b85dc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11EXT_VIRTUAL_STATION_APIS, DOT11EXT_VIRTUAL_STATION_APIS, *PDOT11EXT_VIRTUAL_STATION_APIS
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
req.alt-api: DOT11EXT_VIRTUAL_STATION_APIS
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
req.typenames: DOT11EXT_VIRTUAL_STATION_APIS, *PDOT11EXT_VIRTUAL_STATION_APIS
req.product: Windows 10 or later.
---

# _DOT11EXT_VIRTUAL_STATION_APIS structure



## -description

## -syntax

````
typedef struct _DOT11EXT_VIRTUAL_STATION_APIS {
  DOT11EXT_REQUEST_VIRTUAL_STATION           Dot11ExtRequestVirtualStation;
  DOT11EXT_RELEASE_VIRTUAL_STATION           Dot11ExtReleaseVirtualStation;
  DOT11EXT_QUERY_VIRTUAL_STATION_PROPERTIES  Dot11ExtQueryVirtualStationProperties;
  DOT11EXT_SET_VIRTUAL_STATION_AP_PROPERTIES Dot11ExtSetVirtualStationAPProperties;
} DOT11EXT_VIRTUAL_STATION_APIS, *PDOT11EXT_VIRTUAL_STATION_APIS;
````


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

All of the function pointers are required and must not be set to <b>NULL</b>.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_virtual_station.md">
   Dot11ExtIhvInitVirtualStation</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_query_virtual_station_properties.md">
   Dot11ExtQueryVirtualStationProperties</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_release_virtual_station.md">
   Dot11ExtReleaseVirtualStation</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_request_virtual_station.md">
   Dot11ExtRequestVirtualStation</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_set_virtual_station_ap_properties.md">
   Dot11ExtSetVirtualStationAPProperties</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_VIRTUAL_STATION_APIS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

