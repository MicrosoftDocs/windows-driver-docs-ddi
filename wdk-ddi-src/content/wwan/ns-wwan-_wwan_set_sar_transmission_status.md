---
UID: NS:wwan._WWAN_SET_SAR_TRANSMISSION_STATUS
title: _WWAN_SET_SAR_TRANSMISSION_STATUS (wwan.h)
description: The WWAN_SET_SAR_TRANSMISSION_STATUS structure sets Specific Absorption Rate (SAR) transmission status in a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: 6c80431c-c97b-41c8-969b-fd298e363e9d
ms.date: 08/20/2018
f1_keywords:
 - "wwan/_WWAN_SET_SAR_TRANSMISSION_STATUS"
ms.keywords: _WWAN_SET_SAR_TRANSMISSION_STATUS, WWAN_SET_SAR_TRANSMISSION_STATUS, *PWWAN_SET_SAR_TRANSMISSION_STATUS, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: WWAN_SET_SAR_TRANSMISSION_STATUS, *PWWAN_SET_SAR_TRANSMISSION_STATUS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_SET_SAR_TRANSMISSION_STATUS
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_SET_SAR_TRANSMISSION_STATUS structure

## -description

The **WWAN_SET_SAR_TRANSMISSION_STATUS** structure sets Specific Absorption Rate (SAR) transmission status in a mobile broadband (MBB) modem.

## -struct-fields

### -field ChannelNotification

A [**WWAN_SAR_TRANSMISSION_STATUS_NOTIFICATION_STATE**](ne-wwan-_wwan_sar_transmission_status_notification_state.md) value that specifies whether notifications for SAR transmission are disabled or enabled.
 
### -field HysteresisTimer

A Hysteresis indicator that is used by the modem to determine when to send the a [NDIS_STATUS_WWAN_SAR_TRANSMISSION_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-sar-transmission-status) notification to the host. This value is the timer the modem sees as a continuous no-transmit activity before it sends an OFF indicator to host. This timer should be set in seconds, ranging from 1 second to 5 seconds.

## -remarks

This structure is used in the [**NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_sar_transmission_status.md) structure.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_TRANSMISSION_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-transmission-status)

[NDIS_STATUS_WWAN_SAR_TRANSMISSION_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-sar-transmission-status)

[**NDIS_WWAN_SET_SAR_TRANSMISSION_STATUS**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_sar_transmission_status.md)
