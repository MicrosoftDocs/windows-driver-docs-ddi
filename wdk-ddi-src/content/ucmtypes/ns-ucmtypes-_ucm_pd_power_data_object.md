---
UID: NS:ucmtypes._UCM_PD_POWER_DATA_OBJECT
title: "_UCM_PD_POWER_DATA_OBJECT"
author: windows-driver-content
description: Describes a Power Data Object. For information about these members, see the Power Delivery specification.
old-location: buses\ucm_pd_power_data_object.htm
tech.root: usbref
ms.assetid: C54750A9-EE64-4FE7-9ED6-EC9709A82C43
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: "*PUCM_PD_POWER_DATA_OBJECT, PUCM_PD_POWER_DATA_OBJECT, PUCM_PD_POWER_DATA_OBJECT union pointer [Buses], UCM_PD_POWER_DATA_OBJECT, UCM_PD_POWER_DATA_OBJECT union [Buses], _UCM_PD_POWER_DATA_OBJECT, buses.ucm_pd_power_data_object, ucmtypes/PUCM_PD_POWER_DATA_OBJECT, ucmtypes/UCM_PD_POWER_DATA_OBJECT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtypes.h
api_name:
-	UCM_PD_POWER_DATA_OBJECT
product:
- Windows
targetos: Windows
req.typenames: UCM_PD_POWER_DATA_OBJECT, *PUCM_PD_POWER_DATA_OBJECT
---

# _UCM_PD_POWER_DATA_OBJECT structure


## -description


Describes a Power Data Object. For information about these members, see the <a href="http://www.usb.org/developers/docs/usb20_docs/">Power Delivery specification</a>.


## -struct-fields




### -field Ul

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


### -field FixedSupplyPdo.Reserved

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

Dual role power


### -field FixedSupplyPdo.FixedSupply

fixed supply


### -field VariableSupplyNonBatteryPdo

Contains bitfields describing a variable-supply non-battery PD object.


### -field VariableSupplyNonBatteryPdo.MaximumCurrentIn10mA

Describes the maximum current in multiples of 10 mA.


### -field VariableSupplyNonBatteryPdo.MinimumVoltageIn50mV

Desribes the minimum voltage in multiples of 50 mV.


### -field VariableSupplyNonBatteryPdo.MaximumVoltageIn50mV

Describes the maximum voltage in multiples of 50 mV.


### -field VariableSupplyNonBatteryPdo.VariableSupportNonBattery

Variable Support Non Battery type.


### -field BatterySupplyPdo

Contains bitfields describing a battery supply PD object.


### -field BatterySupplyPdo.MaximumAllowablePowerIn250mW

Describes the maximum allowable power in multiples of 250 mW.


### -field BatterySupplyPdo.MinimumVoltageIn50mV

Describes the minimum voltage in multiples of 50 mV.


### -field BatterySupplyPdo.MaximumVoltageIn50mV

Describes the maximum voltage in multiples of 50 mV.


### -field BatterySupplyPdo.Battery

Battery type.

