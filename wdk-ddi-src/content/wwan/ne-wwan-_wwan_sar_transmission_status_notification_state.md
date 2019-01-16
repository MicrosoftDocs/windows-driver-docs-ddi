---
UID: NE:wwan._WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE
title: _WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE
description: The **WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE** enumeration specifies whether Specific Absorption Rate (SAR) transmission status notifications are disabled or enabled for a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: aa81d0f3-42dd-4e65-a311-ffbb7b2864a1
ms.date: 08/20/2018
ms.topic: enum
ms.keywords: _WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE, WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE, *PWWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE, *PWWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE enumeration

## -description

The **WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE** enumeration specifies whether Specific Absorption Rate (SAR) transmission status notifications are disabled or enabled for a mobile broadband (MBB) modem.

## -enum-fields

### -field WwanTransmissionNotificationDisabled 

Modem channel transmission status notifications are disabled.

### -field WwanTransmissionNotificationEnabled 

Modem channel transmission status notifications are enabled.

## -remarks

This enumeration is used in the [**WWAN_SAR_TRANSMISSION_STATUS_INFO**](ns-wwan-_wwan_sar_transmission_status_info.md) structure and the [**WWAN_SET_SAR_TRANSMISSION_STATUS**](ns-wwan-_wwan_set_sar_transmission_status.md) structure.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_TRANSMISSION_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-transmission-status)

[**WWAN_SAR_TRANSMISSION_STATUS_INFO**](ns-wwan-_wwan_sar_transmission_status_info.md)

[**WWAN_SET_SAR_TRANSMISSION_STATUS**](ns-wwan-_wwan_set_sar_transmission_status.md)
