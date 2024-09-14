---
UID: NE:windot11._DOT11_TEMP_TYPE
title: _DOT11_TEMP_TYPE (windot11.h)
description: The DOT11_TEMP_TYPE enumeration is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
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
---

# _DOT11_TEMP_TYPE enumeration


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_TEMP_TYPE enumeration specifies the operating temperature range of a PHY on the 802.11
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

