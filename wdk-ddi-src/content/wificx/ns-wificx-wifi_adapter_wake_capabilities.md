---
UID: NS:wificx._WIFI_ADAPTER_WAKE_CAPABILITIES
tech.root: netvista
title: WIFI_ADAPTER_WAKE_CAPABILITIES (wificx.h)
ms.date: 09/14/2021
targetos: Windows
description: The WIFI_ADAPTER_WAKE_CAPABILITIES structure describes a WiFiCx net adapter's wake-on-LAN (WoL) capabilities.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_ADAPTER_WAKE_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_ADAPTER_WAKE_CAPABILITIES
 - WIFI_ADAPTER_WAKE_CAPABILITIES
f1_keywords:
 - _WIFI_ADAPTER_WAKE_CAPABILITIES
 - wificx/_WIFI_ADAPTER_WAKE_CAPABILITIES
 - WIFI_ADAPTER_WAKE_CAPABILITIES
 - wificx/WIFI_ADAPTER_WAKE_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **WIFI_ADAPTER_WAKE_CAPABILITIES** structure describes a WiFiCx net adapter's wake-on-LAN (WoL) capabilities.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field NloDiscovery

A boolean value indicating if the net adapter can generate wake-up events due to NLO discovery.

### -field ApAssociationLost

A boolean value indicating if the net adapter can generate wake-up events when access point association is lost.

### -field GtkHandshakeError

A boolean value indicating if the net adapter can generate wake-up events when there is a GTK handshake error.

### -field FourWayHandshakeRequest

A boolean value indicating if the net adapter can generate wake-up events when it receives a 4-Way Handshake request.

## -remarks

Call [**WIFI_ADAPTER_WAKE_CAPABILITIES_INIT**](nf-wificx-wifi_adapter_wake_capabilities_init.md) to initialize this structure. An initialized **WIFI_ADAPTER_WAKE_CAPABILITIES** structure is passed as an input method to [**WifiAdapterSetWakeCapabilities**](nf-wificx-wifiadaptersetwakecapabilities.md).

## -see-also

[**WIFI_ADAPTER_WAKE_CAPABILITIES_INIT**](nf-wificx-wifi_adapter_wake_capabilities_init.md)

[**WifiAdapterSetWakeCapabilities**](nf-wificx-wifiadaptersetwakecapabilities.md)

