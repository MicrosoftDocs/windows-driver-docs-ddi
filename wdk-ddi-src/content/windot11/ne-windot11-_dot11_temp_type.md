---
UID: NE:windot11._DOT11_TEMP_TYPE
title: _DOT11_TEMP_TYPE (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_temp_type.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_TEMP_TYPE enumeration"]
ms.keywords: "*PDOT11_TEMP_TYPE, DOT11_TEMP_TYPE, DOT11_TEMP_TYPE enumeration [Network Drivers Starting with Windows Vista], Native_802.11_data_types_5b580f41-75a6-4d16-9ea5-cc3dc3622a84.xml, PDOT11_TEMP_TYPE, PDOT11_TEMP_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_TEMP_TYPE, dot11_temp_type_1, dot11_temp_type_2, dot11_temp_type_unknown, netvista.dot11_temp_type, windot11/DOT11_TEMP_TYPE, windot11/PDOT11_TEMP_TYPE, windot11/dot11_temp_type_1, windot11/dot11_temp_type_2, windot11/dot11_temp_type_unknown"
req.header: windot11.h
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
targetos: Windows
req.typenames: DOT11_TEMP_TYPE, *PDOT11_TEMP_TYPE
f1_keywords:
 - _DOT11_TEMP_TYPE
 - windot11/_DOT11_TEMP_TYPE
 - PDOT11_TEMP_TYPE
 - windot11/PDOT11_TEMP_TYPE
 - DOT11_TEMP_TYPE
 - windot11/DOT11_TEMP_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_TEMP_TYPE
 - PDOT11_TEMP_TYPE
 - DOT11_TEMP_TYPE
product:
 - Windows 10 or later.
---

# _DOT11_TEMP_TYPE enumeration


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_TEMP_TYPE enumeration specifies the operating temperature range of a PHY on the 802.11
  station.

## -enum-fields

### -field dot11_temp_type_unknown

An uninitialized or unknown temperature type.

### -field dot11_temp_type_1

The commercial temperature range from 0 through 40 degrees Celsius.

### -field dot11_temp_type_2

The industrial temperature range from -30 through 70 degrees Celsius.

## -syntax

```cpp
typedef enum _DOT11_TEMP_TYPE {
  dot11_temp_type_unknown  = 0,
  dot11_temp_type_1        = 1,
  dot11_temp_type_2        = 2
} DOT11_TEMP_TYPE, *PDOT11_TEMP_TYPE;
```

## -remarks

There are different operating temperature requirements dependent on the anticipated environmental
    conditions. The DOT11_TEMP_TYPE enumeration describes a PHY's operating temperature range capability.

## -see-also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/network/oid-dot11-temp-type">OID_DOT11_TEMP_TYPE</a>

