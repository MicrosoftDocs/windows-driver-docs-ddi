---
UID: NS:usbctypes._USBC_PD_REQUEST_DATA_OBJECT
title: _USBC_PD_REQUEST_DATA_OBJECT (usbctypes.h)
description: Describes a Request Data Object (RDO).
ms.assetid: 53d143ae-6a32-4944-a238-e5bd7814ab99
ms.date: 09/30/2018
ms.topic: struct
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbctypes.h
api_name: 
-	_USBC_PD_REQUEST_DATA_OBJECT
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _USBC_PD_REQUEST_DATA_OBJECT structure

## -description
Describes a Request Data Object (RDO). For information about these members, see the [Power Delivery specification](http://www.usb.org/developers/docs/usb20_docs/).

## -struct-fields

### -field U
Size of the structure. 
### -field Common
 
### -field Common.Reserved1
Reserved. 
### -field Common.ObjectPosition
Object position. 
### -field Common.Reserved2
Reserved. 
### -field FixedAndVariableRdo
Contains bitfields describing a request data object.  
### -field FixedAndVariableRdo.MaximumOperatingCurrentIn10mA
Maximum current in 10 mA units. 
### -field FixedAndVariableRdo.OperatingCurrentIn10mA
Operating current in 10mA units. 
### -field FixedAndVariableRdo.Reserved1
Reserved. 
### -field FixedAndVariableRdo.CapabilityMismatch
Capability Mismatch 
### -field FixedAndVariableRdo.GiveBackFlag
GiveBack Flag. 
### -field FixedAndVariableRdo.ObjectPosition
Object Position. 
### -field FixedAndVariableRdo.Reserved2
Reserved for future use. 
### -field BatteryRdo
Contains bitfields describing a request data object. 
### -field BatteryRdo.MaximumOperatingPowerIn250mW
Maximum Operating Power in 250mW units. 
### -field BatteryRdo.OperatingPowerIn250mW
Operating Power in 250mW units. 
### -field BatteryRdo.Reserved1
Reserved. 
### -field BatteryRdo.CapabilityMismatch
Capability Mismatch. 
### -field BatteryRdo.GiveBackFlag
Giveback flag. 
### -field BatteryRdo.ObjectPosition
Object Position. 
### -field BatteryRdo.Reserved2
Reserved. 

## -remarks

## -see-also
