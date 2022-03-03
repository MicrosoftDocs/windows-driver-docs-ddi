---
UID: NS:usbctypes._USBC_PD_REQUEST_DATA_OBJECT
title: _USBC_PD_REQUEST_DATA_OBJECT (usbctypes.h)
description: Describes a request data object (RDO).
tech.root: usbref
ms.date: 02/08/2022
keywords: ["USBC_PD_REQUEST_DATA_OBJECT structure"]
ms.keywords: _USBC_PD_REQUEST_DATA_OBJECT, USBC_PD_REQUEST_DATA_OBJECT, *PUSBC_PD_REQUEST_DATA_OBJECT,
req.header: usbctypes.h
req.include-header: usbctypes.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: USBC_PD_REQUEST_DATA_OBJECT, *PUSBC_PD_REQUEST_DATA_OBJECT
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _USBC_PD_REQUEST_DATA_OBJECT
 - usbctypes/_USBC_PD_REQUEST_DATA_OBJECT
 - PUSBC_PD_REQUEST_DATA_OBJECT
 - usbctypes/PUSBC_PD_REQUEST_DATA_OBJECT
 - USBC_PD_REQUEST_DATA_OBJECT
 - usbctypes/USBC_PD_REQUEST_DATA_OBJECT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbctypes.h
api_name:
 - _USBC_PD_REQUEST_DATA_OBJECT
 - PUSBC_PD_REQUEST_DATA_OBJECT
 - USBC_PD_REQUEST_DATA_OBJECT
---

# _USBC_PD_REQUEST_DATA_OBJECT structure

## -description

Describes a request data object (RDO). For information about these members, see the [Power Delivery specification](https://www.usb.org/documents?search=&tid_2%5B0%5D=40&items_per_page=50).

## -struct-fields

### -field U

Size of the structure.

### -field Common

### -field Common.Reserved1

Reserved, do not use.

### -field Common.ObjectPosition

Object position.

### -field Common.Reserved2

Reserved, do not use.

### -field FixedAndVariableRdo

Contains bit fields describing a request data object.

### -field FixedAndVariableRdo.MaximumOperatingCurrentIn10mA

Maximum current in 10 mA units.

### -field FixedAndVariableRdo.OperatingCurrentIn10mA

Operating current in 10 mA units.

### -field FixedAndVariableRdo.Reserved1

Reserved, do not use.

### -field FixedAndVariableRdo.CapabilityMismatch

Capability mismatch

### -field FixedAndVariableRdo.GiveBackFlag

Giveback flag.

### -field FixedAndVariableRdo.ObjectPosition

Object position.

### -field FixedAndVariableRdo.Reserved2

Reserved, do not use.

### -field BatteryRdo

Contains bit fields describing a request data object.

### -field BatteryRdo.MaximumOperatingPowerIn250mW

Maximum operating power in 250 mW units.

### -field BatteryRdo.OperatingPowerIn250mW

Operating power in 250 mW units.

### -field BatteryRdo.Reserved1

Reserved, do not use.

### -field BatteryRdo.CapabilityMismatch

Capability mismatch.

### -field BatteryRdo.GiveBackFlag

Giveback flag.

### -field BatteryRdo.ObjectPosition

Object position.

### -field BatteryRdo.Reserved2

Reserved, do not use.

### -field ProgrammableRdo

Describes a programmable request data object.

### -field ProgrammableRdo.OperatingCurrentIn50mA

Operating current in 50 mA units.

### -field ProgrammableRdo.Reserved1

Reserved, do not use.

### -field ProgrammableRdo.OutputVoltageIn20mV

Output voltage in 20 mV units.

### -field ProgrammableRdo.Reserved2

Reserved, do not use.

### -field ProgrammableRdo.UnchunkedExtendedMessagesSupported

Supports unchunked extended messages.

### -field ProgrammableRdo.Reserved3

Reserved, do not use.

### -field ProgrammableRdo.CapabilityMismatch

Capability mismatch.

### -field ProgrammableRdo.Reserved4

Reserved, do not use.

### -field ProgrammableRdo.ObjectPosition

Object position.

### -field ProgrammableRdo.Reserved5

Reserved, do not use.

## -remarks

## -see-also
