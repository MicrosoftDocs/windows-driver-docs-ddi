---
UID: NC:wlanihv.DOT11EXTIHV_INIT_VIRTUAL_STATION
title: DOT11EXTIHV_INIT_VIRTUAL_STATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvinitvirtualstation.htm
tech.root: netvista
ms.assetid: 1e18515c-2f24-4690-b5fd-0915ef30307b
ms.date: 02/16/2018
ms.keywords: DOT11EXTIHV_INIT_VIRTUAL_STATION, Dot11ExtIhvInitVirtualStation, Dot11ExtIhvInitVirtualStation callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_1daef8e4-6444-447a-b7a7-0189715a6ab9.xml, netvista.dot11extihvinitvirtualstation, wlanihv/Dot11ExtIhvInitVirtualStation
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtIhvInitVirtualStation
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_INIT_VIRTUAL_STATION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvInitVirtualStation</i> function to initialize the IHV Extensions DLL for virtual station
  operations, and to initialize the API interface between the operating system and the DLL.


## -prototype


```cpp
DOT11EXTIHV_INIT_VIRTUAL_STATION Dot11ExtIhvInitVirtualStation;

DWORD APIENTRY Dot11ExtIhvInitVirtualStation(
  _In_       PDOT11EXT_VIRTUAL_STATION_APIS pDot11ExtVSAPI,
  _Reserved_ LPVOID                         pvReserved
)
{ ... }
```


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

<div class="alert"><b>Note</b>  The IHV Extensions DLL is allowed to call the virtual station API functions that
    the
    <i>pDot11ExtVSAPI</i> parameter points to only after the
    <i>Dot11ExtIhvInitVirtualStation</i> function returns.</div>
<div> </div>
The operating system resolves the address of the
    <i>Dot11ExtIhvInitVirtualStation</i> function by calling the
    <b>GetProcAddress</b> function. As a result, the developer of the IHV Extensions DLL must follow these
    guidelines if this function is implemented.

<ul>
<li>
The DLL must implement a function named Dot11ExtIhvInitVirtualStation, which has the format that is
      described in this topic.

</li>
<li>
The
      <b>EXPORTS</b> statement of the source module-definition (.def) file, which is used to build the IHV
      Extensions DLL, must contain a function name entry for the
      <i>Dot11ExtIhvInitVirtualStation</i> function.

</li>
</ul>
For more information about
    <b>GetProcAddress</b>, see the Microsoft Windows SDK documentation.




## -see-also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_apis.md">DOT11EXT_APIS</a>



<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_handlers.md">DOT11EXT_IHV_HANDLERS</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">Dot11ExtIhvGetVersionInfo</a>



 

 


