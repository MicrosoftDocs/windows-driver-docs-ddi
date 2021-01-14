---
UID: NC:wlanihv.DOT11EXT_REQUEST_VIRTUAL_STATION
title: DOT11EXT_REQUEST_VIRTUAL_STATION (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extrequestvirtualstation.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11EXT_REQUEST_VIRTUAL_STATION callback"]
ms.keywords: DOT11EXT_REQUEST_VIRTUAL_STATION, Dot11ExtRequestVirtualStation, Dot11ExtRequestVirtualStation callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_d118b82f-9abc-4878-b76f-4aabf93b38ea.xml, netvista.dot11extrequestvirtualstation, wlanihv/Dot11ExtRequestVirtualStation
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
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
f1_keywords:
 - DOT11EXT_REQUEST_VIRTUAL_STATION
 - wlanihv/DOT11EXT_REQUEST_VIRTUAL_STATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wlanihv.h
api_name:
 - DOT11EXT_REQUEST_VIRTUAL_STATION
---

# DOT11EXT_REQUEST_VIRTUAL_STATION callback


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtRequestVirtualStation</b> function to request that the operating system
  create a virtual 802.11 station.

## -parameters

### -param hDot11PrimaryHandle 

[in, optional]
A handle used by the operating system to reference the primary physical wireless LAN (WLAN)
     adapter. This handle value was received as the
     <i>hDot11SvcHandle</i> parameter through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

### -param pvReserved

This parameter is reserved for use by the operating system and should be <b>NULL</b>.

## -returns

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.

## -prototype

```cpp
DWORD WINAPI * Dot11ExtRequestVirtualStation(
  _In_opt_   HANDLE hDot11PrimaryHandle,
  _Reserved_ LPVOID pvReserved
);
```

## -remarks

When this request function completes successfully, the operating system begins to process the request
    to create a virtual station. It is possible that the operating system will call the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
    Handler function to initialize the virtual station before or after the call to
    <b>Dot11ExtRequestVirtualStation</b> returns.

After the operating system creates the new virtual station, the IHV Extensions DLL should expect to
    receive a call to the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
    Handler function. In this call, the operating system passes a handle to the new virtual adapter through
    the
    <i>hDot11SvcHandle</i> parameter.

## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_release_virtual_station.md">
   Dot11ExtReleaseVirtualStation</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

