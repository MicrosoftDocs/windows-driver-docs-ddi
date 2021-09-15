---
UID: NE:dot11wificxtypes._WDI_BLUETOOTH_COEXISTENCE_SUPPORT
tech.root: netvista
title: WDI_BLUETOOTH_COEXISTENCE_SUPPORT (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_BLUETOOTH_COEXISTENCE_SUPPORT enum defines Bluetooth coexistence support values.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_BLUETOOTH_COEXISTENCE_SUPPORT
 - WDI_BLUETOOTH_COEXISTENCE_SUPPORT
f1_keywords:
 - _WDI_BLUETOOTH_COEXISTENCE_SUPPORT
 - dot11wificxtypes/_WDI_BLUETOOTH_COEXISTENCE_SUPPORT
 - WDI_BLUETOOTH_COEXISTENCE_SUPPORT
 - dot11wificxtypes/WDI_BLUETOOTH_COEXISTENCE_SUPPORT
dev_langs:
 - c++
---

## -description

The WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration defines Bluetooth coexistence support values.

## -enum-fields

### -field WDI_BLUETOOTH_COEXISTENCE_UNKNOWN:0

Unknown.

### -field WDI_BLUETOOTH_COEXISTENCE_PERFORMANCE_MAINTAINED:1

Wi-Fi and Bluetooth work at the same performance level during coexistence.

### -field WDI_BLUETOOTH_COEXISTENCE_WIFI_DEGRADED_TO_1x1:2

Wi-Fi centered. On a 2X2 device, Wi-Fi and Bluetooth coexists. Wi-Fi performance is reduced to 1X1 level.

### -field WDI_BLUETOOTH_COEXISTENCE_WIFI_THROUGHPUT_DEGRADED:3

Bluetooth centered. When coexisting, Bluetooth has priority and restricts Wi-Fi performance.

### -field WDI_BLUETOOTH_COEXISTENCE_MUTUALLY_EXCLUSIVE:4

Wi-Fi and Bluetooth are mutually exclusive. One of the two stops working.

### -field WDI_BLUETOOTH_COEXISTENCE_MAX:5


## -remarks

## -see-also

