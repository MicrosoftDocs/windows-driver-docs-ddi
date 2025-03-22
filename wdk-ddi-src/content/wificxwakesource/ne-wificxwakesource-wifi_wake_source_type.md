---
UID: NE:wificxwakesource._WIFI_WAKE_SOURCE_TYPE
tech.root: netvista
title: WIFI_WAKE_SOURCE_TYPE (wificxwakesource.h)
ms.date: 03/04/2024
targetos: Windows
description: The WIFI_WAKE_SOURCE_TYPE enumeration specifies the type of a wake-on-LAN (WoL) wake-up event for a WiFiCx net adapter.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wificxwakesource.h
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
 - wificxwakesource.h
api_name:
 - _WIFI_WAKE_SOURCE_TYPE
 - WIFI_WAKE_SOURCE_TYPE
f1_keywords:
 - _WIFI_WAKE_SOURCE_TYPE
 - wificxwakesource/_WIFI_WAKE_SOURCE_TYPE
 - WIFI_WAKE_SOURCE_TYPE
 - wificxwakesource/WIFI_WAKE_SOURCE_TYPE
dev_langs:
 - c++
---

# WIFI_WAKE_SOURCE_TYPE enumeration (wificxwakesource.h)

## -description

The **WIFI_WAKE_SOURCE_TYPE** enumeration specifies the type of a wake-on-LAN (WoL) wake-up event for a WiFiCx net adapter.

## -enum-fields

### -field WifiWakeSourceTypeNloDiscovery

NLO discovery.

### -field WifiWakeSourceTypeApAssociationLost

Access point association lost.

### -field WifiWakeSourceTypeGtkHandshakeError

GTK handshake error.

### -field WifiWakeSourceTypeFourWayHandshakeRequest

4-Way Handshake request.

### -field WifiWakeSourceTypeIncomingActionFrame

Incoming action frame.

### -field WifiWakeSourceTypeClientDriverDiagnostic

Client driver diagnostic event.

## -remarks

## -see-also

