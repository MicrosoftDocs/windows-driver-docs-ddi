---
UID: NE:dot11wificxtypes._WDI_WNM_ACTION
tech.root: netvista
title: WDI_WNM_ACTION
ms.date: 03/07/2024
targetos: Windows
description: "Microsoft reserves the WDI_WNM_ACTION enumeration for internal use only. Don't use this enumeration in your code."
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
 - _WDI_WNM_ACTION
 - WDI_WNM_ACTION
f1_keywords:
 - _WDI_WNM_ACTION
 - dot11wificxtypes/_WDI_WNM_ACTION
 - WDI_WNM_ACTION
 - dot11wificxtypes/WDI_WNM_ACTION
dev_langs:
 - c++
---

# WDI_WNM_ACTION enumeration (dot11wificxtypes.h)

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_WNM_ACTION** enumeration defines the message type for 802.11v BSS Transition Management action frames.

## -enum-fields

### -field WDI_WNM_ACTION_EVENT_REQUEST:0

The message is an event request frame. This is sent by the AP to the client.

### -field WDI_WNM_ACTION_EVENT_RESPONSE:1

The message is an event response frame. This is a response to the above request frame from the AP.

### -field WDI_WNM_ACTION_DIAGNOSTIC_REQUEST:2

The message is a diagnostic request frame. This is sent by the AP to the client.

### -field WDI_WNM_ACTION_DIAGNOSTIC_RESPONSE:3

The message is a diagnostic response frame. This is a response to the above request frame from the AP.

### -field WDI_WNM_ACTION_LOCATION_CONFIGURATION_REQUEST:4

The message is a location configuration request frame. This is sent by the AP to the client.

### -field WDI_WNM_ACTION_LOCATION_CONFIGURATION_RESPONSE:5

The message is a location configuration response frame. This is a response to the above request frame from the AP.

### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY:6

The message is a BSS Transition Management query frame.

### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST:7

The message is a BSS Transition Management request frame. This is sent by the AP to the client.

### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE:8

The message is a BSS Transition Management response frame. This is a response to the above request frame from the AP.


## -remarks

## -see-also

