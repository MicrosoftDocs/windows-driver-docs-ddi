---
UID: NE:dot11wificxtypes._WDI_STOP_AP_REASON
tech.root: netvista
title: WDI_STOP_AP_REASON (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_STOP_AP_REASON enum defines the reasons an adapter cannot sustain 802.11 Access Point (AP) functionality on any of the PHYs.
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
 - _WDI_STOP_AP_REASON
 - WDI_STOP_AP_REASON
f1_keywords:
 - _WDI_STOP_AP_REASON
 - dot11wificxtypes/_WDI_STOP_AP_REASON
 - WDI_STOP_AP_REASON
 - dot11wificxtypes/WDI_STOP_AP_REASON
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) is in maintenance mode and will only receive high priority fixes.

The **WDI_STOP_AP_REASON** enumeration defines the reasons an adapter cannot sustain 802.11 Access Point (AP) functionality on any of the PHYs.

## -enum-fields

### -field WDI_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE:0x0001

The adapter determined that no valid operating frequency is available.

### -field WDI_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE:0x0002

The adapter determined that no operating channel is available.

### -field WDI_STOP_AP_REASON_AP_ACTIVE:0x0003

The adapter determined that an AP is already active on another 802.11 MAC entity for this physical wireless LAN adapter.

### -field WDI_STOP_AP_REASON_IHV_START:0xFF000000

The start value of possible IHV-specified reasons.

### -field WDI_STOP_AP_REASON_IHV_END:0xFFFFFFFF

The end value of possible IHV-specified reasons.

## -remarks

The **WDI_STOP_AP_REASON** enumeration is a value in the [**WDI_TLV_INDICATION_STOP_AP**](/windows-hardware/drivers/netcx/wdi-tlv-indication-stop-ap) TLV.

## -see-also

[**WDI_TLV_INDICATION_STOP_AP**](/windows-hardware/drivers/netcx/wdi-tlv-indication-stop-ap)
