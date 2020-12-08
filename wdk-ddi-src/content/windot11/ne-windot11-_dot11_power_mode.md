---
UID: NE:windot11._DOT11_POWER_MODE
title: _DOT11_POWER_MODE (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_power_mode.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_POWER_MODE enumeration"]
ms.keywords: "*PDOT11_POWER_MODE, DOT11_POWER_MODE, DOT11_POWER_MODE enumeration [Network Drivers Starting with Windows Vista], Native_802.11_data_types_0c9f7464-7651-46e6-910b-2794649d13d0.xml, PDOT11_POWER_MODE, PDOT11_POWER_MODE enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_POWER_MODE, dot11_power_mode_active, dot11_power_mode_powersave, dot11_power_mode_unknown, netvista.dot11_power_mode, windot11/DOT11_POWER_MODE, windot11/PDOT11_POWER_MODE, windot11/dot11_power_mode_active, windot11/dot11_power_mode_powersave, windot11/dot11_power_mode_unknown"
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
req.typenames: DOT11_POWER_MODE, *PDOT11_POWER_MODE
f1_keywords:
 - _DOT11_POWER_MODE
 - windot11/_DOT11_POWER_MODE
 - PDOT11_POWER_MODE
 - windot11/PDOT11_POWER_MODE
 - DOT11_POWER_MODE
 - windot11/DOT11_POWER_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_POWER_MODE
product:
 - Windows 10 or later.
---

# _DOT11_POWER_MODE enumeration


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_POWER_MODE enumeration defines a power management mode for the PHY on the 802.11
  station.

## -enum-fields

### -field dot11_power_mode_unknown

Specifies an undefined or uninitialized power mode.

### -field dot11_power_mode_active

Specifies an active power mode in which the PHY is always turned on.

### -field dot11_power_mode_powersave

Specifies a power-save mode in which the PHY is periodically turned off.

## -syntax

```cpp
typedef enum _DOT11_POWER_MODE {
  dot11_power_mode_unknown    = 0,
  dot11_power_mode_active     = 1,
  dot11_power_mode_powersave  = 2
} DOT11_POWER_MODE, *PDOT11_POWER_MODE;
```

## -remarks

An 802.11 station advertises its power management mode through the Power Management subfield of the
    Frame Control field in the 802.11 MAC header of transmitted frames. For more information about the Power
    Management subfield, refer to Clause 8.2.4.1.7 of the IEEE 802.11-2012 standard.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-enum-association-info">OID_DOT11_ENUM_ASSOCIATION_INFO</a>
