---
UID: NE:dot11wdi._WDI_RX_THROTTLE_LEVEL
title: _WDI_RX_THROTTLE_LEVEL (dot11wdi.h)
description: The WDI_RX_THROTTLE_LEVEL enumeration defines the RX throttle level. The interpretation and implementation mechanisms of these throttle levels are defined by the independent hardware vendor (IHV).
old-location: netvista\wdi_rx_throttle_level.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_RX_THROTTLE_LEVEL enumeration"]
ms.keywords: WDI_RX_THROTTLE_LEVEL, WDI_RX_THROTTLE_LEVEL enumeration [Network Drivers Starting with Windows Vista], WDI_RxThrottleLevelAggressive, WDI_RxThrottleLevelMedium, WDI_RxThrottleLevelNone, _WDI_RX_THROTTLE_LEVEL, dot11wdi/WDI_RX_THROTTLE_LEVEL, dot11wdi/WDI_RxThrottleLevelAggressive, dot11wdi/WDI_RxThrottleLevelMedium, dot11wdi/WDI_RxThrottleLevelNone, netvista.wdi_rx_throttle_level, netvista.wifi_rx_throttle_level
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: WDI_RX_THROTTLE_LEVEL
f1_keywords:
 - _WDI_RX_THROTTLE_LEVEL
 - dot11wdi/_WDI_RX_THROTTLE_LEVEL
 - WDI_RX_THROTTLE_LEVEL
 - dot11wdi/WDI_RX_THROTTLE_LEVEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _WDI_RX_THROTTLE_LEVEL
 - WDI_RX_THROTTLE_LEVEL
---

# _WDI_RX_THROTTLE_LEVEL enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_RX_THROTTLE_LEVEL enumeration defines the RX throttle level. The interpretation and implementation mechanisms of these throttle levels are defined by the independent hardware vendor (IHV).

## -enum-fields

### -field WDI_RxThrottleLevelNone

No throttling.

### -field WDI_RxThrottleLevelMedium

Medium throttling.

### -field WDI_RxThrottleLevelAggressive

Aggressive throttling.

### -field WDI_RxThrottleLevelMax

