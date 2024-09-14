---
UID: NE:windot11._DOT11_POWER_MODE_REASON
title: _DOT11_POWER_MODE_REASON (windot11.h)
description: The DOT11_POWER_MODE_REASON lists the different reasons for changes to auto power save mode state.
old-location: netvista\dot11_power_mode_reason.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_POWER_MODE_REASON enumeration"]
ms.keywords: DOT11_POWER_MODE_REASON, DOT11_POWER_MODE_REASON enumeration [Network Drivers Starting with Windows Vista], _DOT11_POWER_MODE_REASON, dot11_power_mode_reason_compliant_AP, dot11_power_mode_reason_compliant_WFD_device, dot11_power_mode_reason_legacy_WFD_device, dot11_power_mode_reason_no_change, dot11_power_mode_reason_noncompliant_AP, dot11_power_mode_reason_others, netvista.dot11_power_mode_reason, windot11/DOT11_POWER_MODE_REASON, windot11/dot11_power_mode_reason_compliant_AP, windot11/dot11_power_mode_reason_compliant_WFD_device, windot11/dot11_power_mode_reason_legacy_WFD_device, windot11/dot11_power_mode_reason_no_change, windot11/dot11_power_mode_reason_noncompliant_AP, windot11/dot11_power_mode_reason_others
req.header: windot11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.typenames: DOT11_POWER_MODE_REASON
f1_keywords:
 - _DOT11_POWER_MODE_REASON
 - windot11/_DOT11_POWER_MODE_REASON
 - DOT11_POWER_MODE_REASON
 - windot11/DOT11_POWER_MODE_REASON
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_POWER_MODE_REASON
 - DOT11_POWER_MODE_REASON
---

# _DOT11_POWER_MODE_REASON enumeration


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_POWER_MODE_REASON lists the different reasons for changes to auto power save mode  state.

## -enum-fields

### -field dot11_power_mode_reason_no_change

Device is initially in this state and has not changed since.

### -field dot11_power_mode_reason_noncompliant_AP

AP is not compliant. As to be in CAM.

### -field dot11_power_mode_reason_legacy_WFD_device

WFD device is legacy.

### -field dot11_power_mode_reason_compliant_AP

AP is compliant.

### -field dot11_power_mode_reason_compliant_WFD_device

All connected WFD device can do PSM.

### -field dot11_power_mode_reason_others

Other reason.

## -syntax

```cpp
typedef enum _DOT11_POWER_MODE_REASON {
  dot11_power_mode_reason_no_change             = 0,
  dot11_power_mode_reason_noncompliant_AP       = 1,
  dot11_power_mode_reason_legacy_WFD_device     = 2,
  dot11_power_mode_reason_compliant_AP          = 3,
  dot11_power_mode_reason_compliant_WFD_device  = 4,
  dot11_power_mode_reason_others                = 5
} DOT11_POWER_MODE_REASON;
```

