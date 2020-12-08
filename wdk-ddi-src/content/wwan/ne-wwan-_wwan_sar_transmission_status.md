---
UID: NE:wwan._WWAN_SAR_TRANSMISSION_STATUS
title: _WWAN_SAR_TRANSMISSION_STATUS (wwan.h)
description: The WWAN_SAR_TRANSMISSION_STATUS enumeration describes whether a mobile broadband (MBB) modem has transmit (Tx) traffic during its hysteresis timer.
tech.root: netvista
ms.date: 08/20/2018
keywords: ["WWAN_SAR_TRANSMISSION_STATUS enumeration"]
ms.keywords: _WWAN_SAR_TRANSMISSION_STATUS, WWAN_SAR_TRANSMISSION_STATUS, *PWWAN_SAR_TRANSMISSION_STATUS,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WWAN_SAR_TRANSMISSION_STATUS, *PWWAN_SAR_TRANSMISSION_STATUS
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_SAR_TRANSMISSION_STATUS
 - wwan/_WWAN_SAR_TRANSMISSION_STATUS
 - PWWAN_SAR_TRANSMISSION_STATUS
 - wwan/PWWAN_SAR_TRANSMISSION_STATUS
 - WWAN_SAR_TRANSMISSION_STATUS
 - wwan/WWAN_SAR_TRANSMISSION_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SAR_TRANSMISSION_STATUS
---

# _WWAN_SAR_TRANSMISSION_STATUS enumeration


## -description

The **WWAN_SAR_TRANSMISSION_STATUS** enumeration describes whether a mobile broadband (MBB) modem has transmit (Tx) traffic during its hysteresis timer.

## -enum-fields

### -field WwanTransmissionStateInactive 

The modem was not actively transmitting data, without any continuous lapse in transmission, for the last hysteresis timer value.

### -field WwanTransmissionStateActive 

The modem was actively transmitting data.

## -remarks

This enumeration is used in the [**WWAN_SAR_TRANSMISSION_STATUS_INFO**](ns-wwan-_wwan_sar_transmission_status_info.md) structure.

## -see-also

[MB SAR Platform Support](/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_TRANSMISSION_STATUS](/windows-hardware/drivers/network/oid-wwan-sar-transmission-status)

[**WWAN_SAR_TRANSMISSION_STATUS_INFO**](ns-wwan-_wwan_sar_transmission_status_info.md)
