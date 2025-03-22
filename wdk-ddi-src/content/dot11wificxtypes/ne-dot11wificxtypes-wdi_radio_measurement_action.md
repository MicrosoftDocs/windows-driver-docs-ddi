---
UID: NE:dot11wificxtypes._WDI_RADIO_MEASUREMENT_ACTION
tech.root: netvista
title: WDI_RADIO_MEASUREMENT_ACTION
ms.date: 03/08/2024
targetos: Windows
description: The WDI_RADIO_MEASUREMENT_ACTION enumeration defines the radio measurement actions.
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
 - _WDI_RADIO_MEASUREMENT_ACTION
 - WDI_RADIO_MEASUREMENT_ACTION
f1_keywords:
 - _WDI_RADIO_MEASUREMENT_ACTION
 - dot11wificxtypes/_WDI_RADIO_MEASUREMENT_ACTION
 - WDI_RADIO_MEASUREMENT_ACTION
 - dot11wificxtypes/WDI_RADIO_MEASUREMENT_ACTION
dev_langs:
 - c++
---

# WDI_RADIO_MEASUREMENT_ACTION enumeration (dot11wificxtypes.h)

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_RADIO_MEASUREMENT_ACTION** enumeration defines the radio measurement action frames.

## -enum-fields

### -field WDI_RADIO_MEASUREMENT_ACTION_RADIO_MEASUREMENT_REQUEST:0

The message is a radio measurement request action frame sent by the client to the AP.

### -field WDI_RADIO_MEASUREMENT_ACTION_RADIO_MEASUREMENT_REPORT:1

The message is a radio measurement report action frame from the AP.

### -field WDI_RADIO_MEASUREMENT_ACTION_LINK_MEASUREMENT_REQUEST:2

The message is a link measurement request action frame sent by the client to the AP.

### -field WDI_RADIO_MEASUREMENT_ACTION_LINK_MEASUREMENT_RESPONSE:3

The message is a link measurement response action frame from the AP.

### -field WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_REQUEST:4

The message is a neighbor report request action frame sent by the client to the AP.

### -field WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_RESPONSE:5

The message is a neighbor report response action frame from the AP.

## -remarks

## -see-also

[**WDI_ACTION_FRAME_CATEGORY_RADIO_MEASUREMENT**](ne-dot11wificxtypes-wdi_action_frame_category.md)

