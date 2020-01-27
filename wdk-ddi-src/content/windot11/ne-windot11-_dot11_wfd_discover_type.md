---
UID: NE:windot11._DOT11_WFD_DISCOVER_TYPE
title: _DOT11_WFD_DISCOVER_TYPE (windot11.h)
description: The DOT11_WFD_DISCOVER_TYPE enumeration indicates the mode of Wi-Fi Direct device discovery.
old-location: netvista\dot11_wfd_discover_type.htm
tech.root: netvista
ms.assetid: B50C7FD5-5AE4-4BF3-9FD7-F006F4B6BAAF
ms.date: 02/16/2018
ms.keywords: "*PDOT11_WFD_DISCOVER_TYPE, DOT11_WFD_DISCOVER_TYPE, DOT11_WFD_DISCOVER_TYPE enumeration [Network Drivers Starting with Windows Vista], _DOT11_WFD_DISCOVER_TYPE, dot11_wfd_discover_type_auto, dot11_wfd_discover_type_find_only, dot11_wfd_discover_type_forced, dot11_wfd_discover_type_scan_only, dot11_wfd_discover_type_scan_social_channels, netvista.dot11_wfd_discover_type, windot11/DOT11_WFD_DISCOVER_TYPE, windot11/dot11_wfd_discover_type_auto, windot11/dot11_wfd_discover_type_find_only, windot11/dot11_wfd_discover_type_forced, windot11/dot11_wfd_discover_type_scan_only, windot11/dot11_wfd_discover_type_scan_social_channels"
f1_keywords:
 - "windot11/DOT11_WFD_DISCOVER_TYPE"
req.header: windot11.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
- Windot11.h
api_name:
- DOT11_WFD_DISCOVER_TYPE
targetos: Windows
req.typenames: DOT11_WFD_DISCOVER_TYPE, *PDOT11_WFD_DISCOVER_TYPE
product:
- Windows 10 or later.
---

# _DOT11_WFD_DISCOVER_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_DISCOVER_TYPE</b> enumeration indicates  the mode of Wi-Fi Direct device discovery.


## -syntax


```cpp
typedef enum _DOT11_WFD_DISCOVER_TYPE {
  dot11_wfd_discover_type_scan_only             = 1,
  dot11_wfd_discover_type_find_only             = 2,
  dot11_wfd_discover_type_auto                  = 3,
  dot11_wfd_discover_type_scan_social_channels  = 4,
  dot11_wfd_discover_type_forced                = 0x80000000
} DOT11_WFD_DISCOVER_TYPE;
```


## -enum-fields




### -field dot11_wfd_discover_type_scan_only

Device discovery occurs only during the scan phase. During the scan phase, Wi-Fi Direct devices should scan each social channel at least once every 250ms.


### -field dot11_wfd_discover_type_find_only

Device discovery occurs only during the find phase.


### -field dot11_wfd_discover_type_auto

Discovery mode is determined by the driver.


### -field dot11_wfd_discover_type_scan_social_channels

The WFD device must perform device discovery by scanning only P2P social channels. In this setting, the device should scan each social channel at least once every 250ms.


### -field dot11_wfd_discover_type_forced

A flag indicating that a complete device discovery is required. If this flag is not set, a partial discovery can be performed.


## -remarks



The <b>dot11_wfd_discover_type_forced</b> flag may be set along with only one of the other discovery modes.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-discover-request">OID_DOT11_WFD_DISCOVER_REQUEST</a>



<a href="..\windot11\ns-windot11-_dot11_wfd_discover_request.md">DOT11_WFD_DISCOVER_REQUEST</a>



 

 


