---
UID: NS:windot11._DOT11_SUPPORTED_ANTENNA
title: _DOT11_SUPPORTED_ANTENNA (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_antenna.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_SUPPORTED_ANTENNA structure"]
ms.keywords: "*PDOT11_SUPPORTED_ANTENNA, DOT11_SUPPORTED_ANTENNA, DOT11_SUPPORTED_ANTENNA structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_b48dfe45-efbc-4f88-a754-3e1fba8e45f6.xml, PDOT11_SUPPORTED_ANTENNA, PDOT11_SUPPORTED_ANTENNA structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_ANTENNA, netvista.dot11_supported_antenna, windot11/DOT11_SUPPORTED_ANTENNA, windot11/PDOT11_SUPPORTED_ANTENNA"
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
req.typenames: DOT11_SUPPORTED_ANTENNA, *PDOT11_SUPPORTED_ANTENNA
f1_keywords:
 - _DOT11_SUPPORTED_ANTENNA
 - windot11/_DOT11_SUPPORTED_ANTENNA
 - PDOT11_SUPPORTED_ANTENNA
 - windot11/PDOT11_SUPPORTED_ANTENNA
 - DOT11_SUPPORTED_ANTENNA
 - windot11/DOT11_SUPPORTED_ANTENNA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_SUPPORTED_ANTENNA
product:
 - Windows 10 or later.
---

# _DOT11_SUPPORTED_ANTENNA structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SUPPORTED_ANTENNA structure defines an antenna entry in a
  <a href="..\windot11\ns-windot11-_dot11_supported_antenna_list.md">
  DOT11_SUPPORTED_ANTENNA_LIST</a> structure.

## -struct-fields

### -field uAntennaListIndex

A value, from 1 through 255, that uniquely identifies the antenna.

### -field bSupportedAntenna

A Boolean value that indicates, if <b>TRUE</b>, that the antenna referenced by the
     <b>uAntennaListIndex</b> value supports transmit and receive operations.

## -syntax

```cpp
typedef struct _DOT11_SUPPORTED_ANTENNA {
  ULONG   uAntennaListIndex;
  BOOLEAN bSupportedAntenna;
} DOT11_SUPPORTED_ANTENNA, *PDOT11_SUPPORTED_ANTENNA;
```

## -remarks

The meaning of the
    <b>bSupportedAntenna</b> member depends on the OID that it is used with. For example, if
    <b>bSupportedAntenna</b> is <b>TRUE</b> when an antenna list is queried through
    <a href="/previous-versions/ms893804(v=msdn.10)">OID_DOT11_SUPPORTED_RX_ANTENNA</a>,
    the antenna referenced by the
    <b>uAntennaListIndex</b> member is supported for receive operations.

## -see-also

<a href="..\windot11\ns-windot11-_dot11_supported_antenna_list.md">DOT11_SUPPORTED_ANTENNA_LIST</a>



<a href="/previous-versions/windows/embedded/ee484405(v=winembedded.80)">OID_DOT11_SUPPORTED_TX_ANTENNA</a>



<a href="/previous-versions/ms893804(v=msdn.10)">OID_DOT11_SUPPORTED_RX_ANTENNA</a>
