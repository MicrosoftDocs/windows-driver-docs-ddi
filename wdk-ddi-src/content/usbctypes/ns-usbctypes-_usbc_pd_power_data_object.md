---
UID: NS:usbctypes._USBC_PD_POWER_DATA_OBJECT
title: _USBC_PD_POWER_DATA_OBJECT (usbctypes.h)
description: Describes a Power Data Object (PDO).
ms.assetid: b1a69368-f613-4e03-b350-287e770a05a6
ms.date: 09/30/2018
keywords: ["_USBC_PD_POWER_DATA_OBJECT structure"]
f1_keywords:
 - "usbctypes/_USBC_PD_POWER_DATA_OBJECT"
 - "_USBC_PD_POWER_DATA_OBJECT"
ms.keywords: _USBC_PD_POWER_DATA_OBJECT, USBC_PD_POWER_DATA_OBJECT, *PUSBC_PD_POWER_DATA_OBJECT, 
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
req.typenames: USBC_PD_POWER_DATA_OBJECT, *PUSBC_PD_POWER_DATA_OBJECT
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbctypes.h
api_name: 
- _USBC_PD_POWER_DATA_OBJECT
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _USBC_PD_POWER_DATA_OBJECT structure

## -description
Describes a Power Data Object (PDO). For information about these members, see the [Power Delivery specification](https://www.usb.org/documents?search=&tid_2%5B0%5D=40&items_per_page=50).

## -struct-fields

### -field U
Size of the structure. 
### -field Common
 
### -field Common.Reserved
Reserved. 
### -field Common.Type
Type of Power Data Object. 
### -field FixedSupplyPdo
 Describing a Fixed Supply type Power Data Object.
### -field FixedSupplyPdo.MaximumCurrentIn10mA
Maximum current in multiples of 10 mA. 
### -field FixedSupplyPdo.VoltageIn50mV
Voltage in multiples of 50 mV. 
### -field FixedSupplyPdo.PeakCurrent
Peak current. 
### -field FixedSupplyPdo.Reserved1
Reserved for future use. 
### -field FixedSupplyPdo.DataRoleSwap
If set, indicates the Power Data Object can perform a data role swap. 
### -field FixedSupplyPdo.UsbCommunicationCapable
If set, indicates the Power Data Object is USB communication capable. 
### -field FixedSupplyPdo.ExternallyPowered
If set, indicates the Power Data Object is externally powered. 
### -field FixedSupplyPdo.UsbSuspendSupported
Indicates support for USB suspend. 
### -field FixedSupplyPdo.DualRolePower
Dual role power. 
### -field FixedSupplyPdo.FixedSupply
Fixed supply.
### -field BatterySupplyPdo
Contains bitfields describing a variable-supply non-battery PD object. 
### -field BatterySupplyPdo.MaximumAllowablePowerIn250mW
Describes the maximum voltage in multiples of 250mV.
### -field BatterySupplyPdo.MinimumVoltageIn50mV
Describes the minimum voltage in multiples of 50mV. 
### -field BatterySupplyPdo.MaximumVoltageIn50mV
Describes the maximum voltage in multiples of 50mV. 
### -field BatterySupplyPdo.Battery
Battery type.
### -field VariableSupplyNonBatteryPdo
Contains bitfields describing a variable-supply non-battery PD object. 
### -field VariableSupplyNonBatteryPdo.MaximumCurrentIn10mA
Describes the maximum current in multiples of 10 mA. 
### -field VariableSupplyNonBatteryPdo.MinimumVoltageIn50mV
Describes the maximum current in multiples of 50 mA. 
### -field VariableSupplyNonBatteryPdo.MaximumVoltageIn50mV
Describes the maximum voltage in multiples of 10 mA. 
### -field VariableSupplyNonBatteryPdo.VariableSupportNonBattery
Variable Support Non Battery type. 
### -field FixedSupplyPdoSink
Describing a Fixed Supply type Power Data Object. 
### -field FixedSupplyPdoSink.OperationalCurrentIn10mA
 
### -field FixedSupplyPdoSink.VoltageIn50mV
Voltage in multiples of 50 mV. 
### -field FixedSupplyPdoSink.Reserved
Reserved. 
### -field FixedSupplyPdoSink.DataRoleSwap
If set, indicates the Power Data Object can perform a data role swap. 
### -field FixedSupplyPdoSink.UsbCommunicationCapable
If set, indicates the Power Data Object is USB communication capable. 
### -field FixedSupplyPdoSink.ExternallyPowered
If set, indicates the Power Data Object is externally powered. 
### -field FixedSupplyPdoSink.HigherCapability
 
### -field FixedSupplyPdoSink.DualRolePower
Dual role power. 
### -field FixedSupplyPdoSink.FixedSupply
Fixed supply. 
### -field BatterySupplyPdoSink
Contains bitfields describing a variable-supply non-battery PD object.  
### -field BatterySupplyPdoSink.OperationalPowerIn250mW
Describes the maximum voltage in multiples of 250mV. 
### -field BatterySupplyPdoSink.MinimumVoltageIn50mV
Describes the minimum voltage in multiples of 50mV.  
### -field BatterySupplyPdoSink.MaximumVoltageIn50mV
Describes the maximum voltage in multiples of 50mV.  
### -field BatterySupplyPdoSink.Battery
Battery type. 
### -field VariableSupplyNonBatteryPdoSink
Contains bitfields describing a battery supply PD object. 
### -field VariableSupplyNonBatteryPdoSink.OperationalCurrentIn10mA
 
### -field VariableSupplyNonBatteryPdoSink.MinimumVoltageIn50mV
Describes the minimum voltage in multiples of 50mV.   
### -field VariableSupplyNonBatteryPdoSink.MaximumVoltageIn50mV
Describes the maximum voltage in multiples of 50mV.   
### -field VariableSupplyNonBatteryPdoSink.VariableSupportNonBattery
Variable Support Non Battery type. 

## -remarks

## -see-also
