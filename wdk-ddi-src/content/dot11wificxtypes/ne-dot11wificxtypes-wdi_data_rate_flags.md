---
UID: NE:dot11wificxtypes._WDI_DATA_RATE_FLAGS
tech.root: netvista
title: WDI_DATA_RATE_FLAGS (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_DATA_RATE_FLAGS enum defines the data rate flags.
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
 - _WDI_DATA_RATE_FLAGS
 - WDI_DATA_RATE_FLAGS
f1_keywords:
 - _WDI_DATA_RATE_FLAGS
 - dot11wificxtypes/_WDI_DATA_RATE_FLAGS
 - WDI_DATA_RATE_FLAGS
 - dot11wificxtypes/WDI_DATA_RATE_FLAGS
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_DATA_RATE_FLAGS** enumeration defines the data rate flags.

## -enum-fields

### -field WDI_DATA_RATE_NON_STANDARD:0x01

The data rate is not a standard data rate defined in the IEEE 802.11 standards.

### -field WDI_DATA_RATE_RX_RATE:0x02

The data rate can be used for RX.

### -field WDI_DATA_RATE_TX_RATE:0x04

The data rate can be used for TX.

## -remarks

The **WDI_DATA_RATE_FLAGS** enum is a member of the [**WDI_DATA_RATE_ENTRY**](ns-dot11wificxtypes-wdi_data_rate_entry.md) structure.


## -see-also

[**WDI_DATA_RATE_ENTRY**](ns-dot11wificxtypes-wdi_data_rate_entry.md)
