---
UID: NC:wlanihv.DOT11EXT_RELEASE_VIRTUAL_STATION
title: DOT11EXT_RELEASE_VIRTUAL_STATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extreleasevirtualstation.htm
old-project: netvista
ms.assetid: 39a907ba-18dc-4e74-a35d-dbf96ef47287
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtReleaseVirtualStation
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
req.typenames: *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_RELEASE_VIRTUAL_STATION callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtReleaseVirtualStation(
  _In_opt_   HANDLE hDot11PrimaryHandle,
  _Reserved_ LPVOID pvReserved
);
````


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
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_request_virtual_station.md">
   Dot11ExtRequestVirtualStation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_RELEASE_VIRTUAL_STATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

