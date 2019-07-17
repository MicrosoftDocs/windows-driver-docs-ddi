---
UID: NC:wlanihv.DOT11EXT_RELEASE_VIRTUAL_STATION
title: DOT11EXT_RELEASE_VIRTUAL_STATION (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extreleasevirtualstation.htm
tech.root: netvista
ms.assetid: 39a907ba-18dc-4e74-a35d-dbf96ef47287
ms.date: 02/16/2018
ms.keywords: DOT11EXT_RELEASE_VIRTUAL_STATION, Dot11ExtReleaseVirtualStation, Dot11ExtReleaseVirtualStation callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_3fe2f0cd-336a-4272-8d14-1ab400515de5.xml, netvista.dot11extreleasevirtualstation, wlanihv/Dot11ExtReleaseVirtualStation
ms.topic: callback
f1_keywords:
 - "wlanihv/Dot11ExtReleaseVirtualStation"
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wlanihv.h
api_name:
- Dot11ExtReleaseVirtualStation
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_RELEASE_VIRTUAL_STATION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtReleaseVirtualStation</b> function to release a prior
  <a href="..\wlanihv\nc-wlanihv-dot11ext_request_virtual_station.md">
  Dot11ExtRequestVirtualStation</a> request to create an 802.11 virtual station.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtReleaseVirtualStation(
  _In_opt_   HANDLE hDot11PrimaryHandle,
  _Reserved_ LPVOID pvReserved
);
```


## -parameters




### -param hDot11PrimaryHandle [in, optional]

The handle used by the operating system to reference the primary physical wireless LAN (WLAN)
     adapter. This handle value was received as the
     <i>hDot11SvcHandle</i> parameter through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function. It is also the
     <i>hDot11PrimaryHandle</i> parameter that the IHV Extension DLL used in a previous call to
     <a href="..\wlanihv\nc-wlanihv-dot11ext_request_virtual_station.md">
     Dot11ExtRequestVirtualStation</a>.


### -param pvReserved

This parameter is reserved for use by the operating system and should be <b>NULL</b>.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The operating system can ignore a call to the
    <b>Dot11ExtReleaseVirtualStation</b> function if the virtual 802.11 station is
    still needed, or if the operating system is already processing a request to remove the virtual
    station.

When this release function completes successfully, the virtual station has been deleted, or the operating system is in the process of deleting the virtual station.

A call to
    <b>Dot11ExtReleaseVirtualStation</b> informs the operating system that the
    virtual station is no longer requested by the IHV Extensions DLL. However, the IHV Extensions DLL should
    not uninitialize any data that is specific to the virtual station until it receives a call to the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a> IHV
    Handler function.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_request_virtual_station.md">
   Dot11ExtRequestVirtualStation</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


