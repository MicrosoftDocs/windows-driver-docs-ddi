---
UID: NC:wlanihv.DOT11EXT_SET_EXCLUDE_UNENCRYPTED
title: DOT11EXT_SET_EXCLUDE_UNENCRYPTED
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetexcludeunencrypted.htm
tech.root: netvista
ms.assetid: b6482124-0d65-4953-8a8f-a09c0a88d830
ms.date: 02/16/2018
ms.keywords: DOT11EXT_SET_EXCLUDE_UNENCRYPTED, Dot11ExtSetExcludeUnencrypted, Dot11ExtSetExcludeUnencrypted callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_aa6f594d-e5b7-4ba0-9ad8-deb42f6c23ad.xml, netvista.dot11extsetexcludeunencrypted, wlanihv/Dot11ExtSetExcludeUnencrypted
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtSetExcludeUnencrypted
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_EXCLUDE_UNENCRYPTED callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtSetExcludeUnencrypted</b> function to enable or disable the wireless
  LAN (WLAN) adapter from excluding unencrypted packets it receives while enabled for cipher
  operations.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtSetExcludeUnencrypted(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     BOOL   bExcludeUnencrypted
);
```


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param bExcludeUnencrypted [in]

A Boolean value that, if set to <b>TRUE</b>, configures the WLAN adapter to exclude unencrypted
     packets.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



If the WLAN adapter is enabled to exclude unencrypted packets, the station must exempt received
    packets that match an entry in the station's current EtherType exemption list. The IHV Extensions DLL
    specifies the EtherType exemption list through calls to the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">
    Dot11ExtSetEtherTypeHandling</a> function.

A call to the
    <b>Dot11ExtSetExcludeUnencrypted</b> function results in a set request of the
    <a href="https://msdn.microsoft.com/library/gg159162.aspx">
    OID_DOT11_EXCLUDE_UNENCRYPTED</a> object identifier (OID) to the Native 802.11 miniport driver that
    manages the WLAN adapter.




## -see-also

<a href="https://msdn.microsoft.com/library/gg159162.aspx">OID_DOT11_EXCLUDE_UNENCRYPTED</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


