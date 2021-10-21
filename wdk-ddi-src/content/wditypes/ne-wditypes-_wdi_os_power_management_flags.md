---
UID: NE:wditypes._WDI_OS_POWER_MANAGEMENT_FLAGS
title: _WDI_OS_POWER_MANAGEMENT_FLAGS (wditypes.h)
description: The WDI_OS_POWER_MANAGEMENT_FLAGS enumeration defines supported enablement scenarios of the NIC Auto Power Saver (NAPS) OS power management feature.
tech.root: netvista
ms.date: 03/30/2018
keywords: ["WDI_OS_POWER_MANAGEMENT_FLAGS enumeration"]
ms.keywords: _WDI_OS_POWER_MANAGEMENT_FLAGS, WDI_OS_POWER_MANAGEMENT_FLAGS,
req.header: wditypes.hpp
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WDI_OS_POWER_MANAGEMENT_FLAGS
targetos: Windows
f1_keywords:
 - _WDI_OS_POWER_MANAGEMENT_FLAGS
 - wditypes/_WDI_OS_POWER_MANAGEMENT_FLAGS
 - WDI_OS_POWER_MANAGEMENT_FLAGS
 - wditypes/WDI_OS_POWER_MANAGEMENT_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_OS_POWER_MANAGEMENT_FLAGS
 - WDI_OS_POWER_MANAGEMENT_FLAGS
---

# _WDI_OS_POWER_MANAGEMENT_FLAGS enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The **WDI_OS_POWER_MANAGEMENT_FLAGS** enumeration defines supported enablement scenarios of the NIC Auto Power Saver (NAPS) OS power management feature.

## -enum-fields

### -field WDI_OS_POWER_MANAGEMENT_NONE 

Enable no OS NAPS power management features.

### -field WDI_OS_POWER_MANAGEMENT_ENABLE_STANDBY_NAPS 

Enable NAPS mode for screen off, modern standby (if supported by hardware).

### -field WDI_OS_POWER_MANAGEMENT_ENABLE_S0_NAPS 

Enable NAPS mode for screen on *S0* system power state (if supported by hardware).

## -remarks

This enumeration is used as the value type in [WDI_TLV_OS_POWER_MANAGEMENT_FEATURES](/windows-hardware/drivers/network/wdi-tlv-os-power-management-features).

## -see-also

