---
UID: NE:usbctypes._USBC_PD_POWER_DATA_OBJECT_TYPE
title: _USBC_PD_POWER_DATA_OBJECT_TYPE (usbctypes.h)
description: Learn how USBC_PD_POWER_DATA_OBJECT_TYPE defines power data object (PDO) types.
tech.root: usbref
ms.date: 02/08/2022
keywords: ["USBC_PD_POWER_DATA_OBJECT_TYPE enumeration"]
ms.keywords: _USBC_PD_POWER_DATA_OBJECT_TYPE, USBC_PD_POWER_DATA_OBJECT_TYPE,
req.header: usbctypes.h
req.include-header: usbctypes.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance: 
req.max-support: 
req.typenames: USBC_PD_POWER_DATA_OBJECT_TYPE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _USBC_PD_POWER_DATA_OBJECT_TYPE
 - usbctypes/_USBC_PD_POWER_DATA_OBJECT_TYPE
 - USBC_PD_POWER_DATA_OBJECT_TYPE
 - usbctypes/USBC_PD_POWER_DATA_OBJECT_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbctypes.h
api_name:
 - _USBC_PD_POWER_DATA_OBJECT_TYPE
 - USBC_PD_POWER_DATA_OBJECT_TYPE
---

# _USBC_PD_POWER_DATA_OBJECT_TYPE enumeration

## -description

Defines power data object (PDO) types.

## -enum-fields

### -field UsbCPdPdoTypeFixedSupply

Indicates the PD data object type is a fixed supply.

### -field UsbCPdPdoTypeBatterySupply

Indicates the PD data object type is a battery supply.

### -field UsbCPdPdoTypeVariableSupplyNonBattery

Indicates the PD data object type is a non-battery variable supply.

### -field UsbCPdPdoTypeAugmentedPowerDataObject

Indicates the PD data object type is an augmented supply.

## -remarks

For information about these members, see the [Power Delivery specification](https://www.usb.org/documents?search=&tid_2%5B0%5D=40&items_per_page=50).

## -see-also

- [_USBC_PD_AUGMENTED_POWER_DATA_OBJECT_TYPE](ne-usbctypes-usbc_pd_augmented_power_data_object_type.md)
