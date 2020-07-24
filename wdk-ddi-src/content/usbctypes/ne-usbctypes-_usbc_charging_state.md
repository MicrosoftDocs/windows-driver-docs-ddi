---
UID: NE:usbctypes._USBC_CHARGING_STATE
title: _USBC_CHARGING_STATE (usbctypes.h)
description: Defines the charging state of a Type-C connector.
ms.assetid: dc25a168-6fc0-49a6-8b68-e01451a06b45
ms.date: 09/30/2018
keywords: ["_USBC_CHARGING_STATE enumeration"]
f1_keywords:
 - "usbctypes/_USBC_CHARGING_STATE"
 - "_USBC_CHARGING_STATE"
ms.keywords: _USBC_CHARGING_STATE, USBC_CHARGING_STATE, 
req.header: usbctypes.h
req.include-header: usbctypes.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance:
req.max-support:
req.typenames: USBC_CHARGING_STATE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbctypes.h
api_name: 
- _USBC_CHARGING_STATE
targetos: Windows
ms.custom: RS5
---

# _USBC_CHARGING_STATE enumeration

## -description
Defines the charging state of a Type-C connector.

## -enum-fields

### -field UsbCChargingStateInvalid
Indicates the charging state is invalid. 
 
### -field UsbCChargingStateNotCharging 
Indicates the port is not drawing a charge. 

### -field UsbCChargingStateNominalCharging
Indicates the port is drawing a nominal charge. 

### -field UsbCChargingStateSlowCharging 
Indicates the port is drawing a slow charge. 

### -field UsbCChargingStateTrickleCharging 
Indicates the port is drawing a trickle charge.

## -remarks

## -see-also
