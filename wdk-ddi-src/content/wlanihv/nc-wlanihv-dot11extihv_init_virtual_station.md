---
UID: NC:wlanihv.DOT11EXTIHV_INIT_VIRTUAL_STATION
title: DOT11EXTIHV_INIT_VIRTUAL_STATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvinitvirtualstation.htm
old-project: netvista
ms.assetid: 1e18515c-2f24-4690-b5fd-0915ef30307b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
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
req.alt-api: Dot11ExtIhvInitVirtualStation
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

# DOT11EXTIHV_INIT_VIRTUAL_STATION callback



## -description

## -prototype

````
DOT11EXTIHV_INIT_VIRTUAL_STATION Dot11ExtIhvInitVirtualStation;

DWORD APIENTRY Dot11ExtIhvInitVirtualStation(
  _In_       PDOT11EXT_VIRTUAL_STATION_APIS pDot11ExtVSAPI,
  _Reserved_ LPVOID                         pvReserved
)
{ ... }
````


## -parameters

### -param pDot11ExtVSAPI [in]

A pointer to a 
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_virtual_station_apis.md">
     DOT11EXT_VIRTUAL_STATION_APIS</a> structure, which contains the addresses of the IHV Extensibility
     virtual station functions that are supported by the operating system. The operating system formats this
     parameter with the function addresses before making a call to the 
     <i>Dot11ExtIhvInitVirtualStation</i> function.


### -param pvReserved 

This parameter is reserved for use by the operating system and should be <b>NULL</b>.


## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.


## -remarks
It is optional for the IHV Extensions DLL to implement and export this function.

The operating system calls the 
    <i>Dot11ExtIhvInitVirtualStation</i> function immediately after it calls the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a> function,
    but before it calls the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">
    Dot11ExtIhvInitAdapter</a> function.

In response to a call to 
    <i>Dot11ExtIhvInitVirtualStation</i>, the IHV Extensions DLL can initialize its internal data structures
    with the information provided from the 
    <i>Dot11ExtIhvInitService</i> function call.

The operating system resolves the address of the 
    <i>Dot11ExtIhvInitVirtualStation</i> function by calling the 
    <b>GetProcAddress</b> function. As a result, the developer of the IHV Extensions DLL must follow these
    guidelines if this function is implemented.

The DLL must implement a function named Dot11ExtIhvInitVirtualStation, which has the format that is
      described in this topic.

The 
      <b>EXPORTS</b> statement of the source module-definition (.def) file, which is used to build the IHV
      Extensions DLL, must contain a function name entry for the 
      <i>Dot11ExtIhvInitVirtualStation</i> function.

For more information about 
    <b>GetProcAddress</b>, see the Microsoft Windows SDK documentation.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11ext_apis.md">DOT11EXT_APIS</a>
</dt>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_handlers.md">DOT11EXT_IHV_HANDLERS</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">Dot11ExtIhvGetVersionInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_INIT_VIRTUAL_STATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

