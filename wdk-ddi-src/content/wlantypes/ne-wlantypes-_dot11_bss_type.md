---
UID: NE:wlantypes._DOT11_BSS_TYPE
title: _DOT11_BSS_TYPE (wlantypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_bss_type.htm
tech.root: netvista
ms.assetid: 5cb263e2-e5b7-456f-9fef-deaf5434c404
ms.date: 02/16/2018
keywords: ["DOT11_BSS_TYPE enumeration"]
ms.keywords: "*PDOT11_BSS_TYPE, DOT11_BSS_TYPE, DOT11_BSS_TYPE enumeration [Network Drivers Starting with Windows Vista], Native_802.11_data_types_ac59d6f5-1095-4953-8079-7f616769a3fa.xml, PDOT11_BSS_TYPE, PDOT11_BSS_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_BSS_TYPE, dot11_BSS_type_any, dot11_BSS_type_independent, dot11_BSS_type_infrastructure, netvista.dot11_bss_type, wlantypes/DOT11_BSS_TYPE, wlantypes/PDOT11_BSS_TYPE, wlantypes/dot11_BSS_type_any, wlantypes/dot11_BSS_type_independent, wlantypes/dot11_BSS_type_infrastructure"
f1_keywords:
 - "wlantypes/DOT11_BSS_TYPE"
 - "DOT11_BSS_TYPE"
req.header: wlantypes.h
req.include-header: Ndis.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wlantypes.h
api_name:
- DOT11_BSS_TYPE
targetos: Windows
req.typenames: DOT11_BSS_TYPE, *PDOT11_BSS_TYPE
req.product: Windows 10 or later.
---

# _DOT11_BSS_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_BSS_TYPE enumeration defines a basic service set (BSS) network type.


## -syntax


```cpp
typedef enum _DOT11_BSS_TYPE {
  dot11_BSS_type_infrastructure  = 1,
  dot11_BSS_type_independent     = 2,
  dot11_BSS_type_any             = 3
} DOT11_BSS_TYPE, *PDOT11_BSS_TYPE;
```


## -enum-fields




### -field dot11_BSS_type_infrastructure

Specifies an infrastructure BSS network.


### -field dot11_BSS_type_independent

Specifies an independent BSS (IBSS) network.


### -field dot11_BSS_type_any

Specifies either infrastructure or IBSS network.


## -remarks



The
    <b>dot11_BSS_type_any</b> enumerator is valid only if it is specified when
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-scan-request">OID_DOT11_SCAN_REQUEST</a> is set.
    <b>dot11_BSS_type_any</b> is used to request a scan for all types of BSSs that are visible to the 802.11
    station.




## -see-also

<a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-wlantimedconnectrequest">
   NDIS_STATUS_DOT11_CONNECTION_START</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-desired-bss-type">OID_DOT11_DESIRED_BSS_TYPE</a>



<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-enum-bss-list">OID_DOT11_ENUM_BSS_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-scan-request">OID_DOT11_SCAN_REQUEST</a>



 

 


