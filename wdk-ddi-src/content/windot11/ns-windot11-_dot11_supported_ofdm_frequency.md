---
UID: NS:windot11._DOT11_SUPPORTED_OFDM_FREQUENCY
title: _DOT11_SUPPORTED_OFDM_FREQUENCY (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_ofdm_frequency.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_SUPPORTED_OFDM_FREQUENCY structure"]
ms.keywords: "*PDOT11_SUPPORTED_OFDM_FREQUENCY, DOT11_SUPPORTED_OFDM_FREQUENCY, DOT11_SUPPORTED_OFDM_FREQUENCY structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_5a7cc235-128d-4209-a250-49ec0b2b8ad7.xml, PDOT11_SUPPORTED_OFDM_FREQUENCY, PDOT11_SUPPORTED_OFDM_FREQUENCY structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_OFDM_FREQUENCY, netvista.dot11_supported_ofdm_frequency, windot11/DOT11_SUPPORTED_OFDM_FREQUENCY, windot11/PDOT11_SUPPORTED_OFDM_FREQUENCY"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
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
targetos: Windows
req.typenames: DOT11_SUPPORTED_OFDM_FREQUENCY, *PDOT11_SUPPORTED_OFDM_FREQUENCY
f1_keywords:
 - _DOT11_SUPPORTED_OFDM_FREQUENCY
 - windot11/_DOT11_SUPPORTED_OFDM_FREQUENCY
 - PDOT11_SUPPORTED_OFDM_FREQUENCY
 - windot11/PDOT11_SUPPORTED_OFDM_FREQUENCY
 - DOT11_SUPPORTED_OFDM_FREQUENCY
 - windot11/DOT11_SUPPORTED_OFDM_FREQUENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_SUPPORTED_OFDM_FREQUENCY
product:
 - Windows 10 or later.
---

# _DOT11_SUPPORTED_OFDM_FREQUENCY structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SUPPORTED_OFDM_FREQUENCY structure specifies a supported channel center frequency entry in
  a
  <a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency_list.md">
  DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a> structure.

## -struct-fields

### -field uCenterFrequency

A ULONG value that represents a channel center frequency, in MHz, that the 802.11 station can
     operate with.

## -syntax

```cpp
typedef struct _DOT11_SUPPORTED_OFDM_FREQUENCY {
  ULONG uCenterFrequency;
} DOT11_SUPPORTED_OFDM_FREQUENCY, *PDOT11_SUPPORTED_OFDM_FREQUENCY;
```

## -see-also

<a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency_list.md">
   DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a>
