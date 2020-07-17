---
UID: NS:windot11._DOT11_WFD_CONFIGURATION_TIMEOUT
title: _DOT11_WFD_CONFIGURATION_TIMEOUT (windot11.h)
description: The DOT11_WFD_CONFIGURATION_TIMEOUT structure contains configuration time-out parameters.
old-location: netvista\dot11_wfd_configuration_timeout.htm
tech.root: netvista
ms.assetid: 5432EB69-933A-4080-919F-4131DC4044D0
ms.date: 02/16/2018
keywords: ["_DOT11_WFD_CONFIGURATION_TIMEOUT structure"]
ms.keywords: "*PDOT11_WFD_CONFIGURATION_TIMEOUT, DOT11_WFD_CONFIGURATION_TIMEOUT, DOT11_WFD_CONFIGURATION_TIMEOUT structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_CONFIGURATION_TIMEOUT, PDOT11_WFD_CONFIGURATION_TIMEOUT structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_CONFIGURATION_TIMEOUT, netvista.dot11_wfd_configuration_timeout, windot11/DOT11_WFD_CONFIGURATION_TIMEOUT, windot11/PDOT11_WFD_CONFIGURATION_TIMEOUT"
f1_keywords:
 - "windot11/DOT11_WFD_CONFIGURATION_TIMEOUT"
 - "DOT11_WFD_CONFIGURATION_TIMEOUT"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
- DOT11_WFD_CONFIGURATION_TIMEOUT
targetos: Windows
req.typenames: DOT11_WFD_CONFIGURATION_TIMEOUT, *PDOT11_WFD_CONFIGURATION_TIMEOUT
product:
- Windows 10 or later.
---

# _DOT11_WFD_CONFIGURATION_TIMEOUT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_CONFIGURATION_TIMEOUT</b> structure contains configuration time-out parameters.


## -syntax


```cpp
typedef struct _DOT11_WFD_CONFIGURATION_TIMEOUT {
  UCHAR GOTimeout;
  UCHAR ClientTimeout;
} DOT11_WFD_CONFIGURATION_TIMEOUT, *PDOT11_WFD_CONFIGURATION_TIMEOUT;
```


## -struct-fields




### -field GOTimeout

The time, in milliseconds, allowed to configure as a Group Owner (GO). The miniport must convert this value to the correct units before including it in a Peer-to-Peer Information Element (P2P IE).


### -field ClientTimeout

The time, in milliseconds, allowed to configure as a client. The miniport must convert this value to the correct units before including it in a P2P IE.

