---
UID: NS:ucmtypes._UCM_PD_POWER_DATA_OBJECT
title: _UCM_PD_POWER_DATA_OBJECT
author: windows-driver-content
description: Describes a Power Data Object. For information about these members, see the Power Delivery specification.
old-location: buses\ucm_pd_power_data_object.htm
old-project: usbref
ms.assetid: C54750A9-EE64-4FE7-9ED6-EC9709A82C43
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _UCM_PD_POWER_DATA_OBJECT, *PUCM_PD_POWER_DATA_OBJECT, UCM_PD_POWER_DATA_OBJECT
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
req.alt-api: UCM_PD_POWER_DATA_OBJECT
req.alt-loc: ucmtypes.h
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
req.typenames: *PUCM_PD_POWER_DATA_OBJECT, UCM_PD_POWER_DATA_OBJECT
req.product: Windows 10 or later.
---

# _UCM_PD_POWER_DATA_OBJECT structure



## -description
Describes a Power Data Object. For information about these members, see the <a href="http://www.usb.org/developers/docs/usb20_docs/#usb20spec">Power Delivery specification</a>.



## -syntax

````
typedef union _UCM_PD_POWER_DATA_OBJECT {
  Ulong  Ul;
  struct {
    unsigned Reserved  :30;
    unsigned Type  :2;
  } Common;
  struct {
    unsigned MaximumCurrentIn10mA  :10;
    unsigned VoltageIn50mV  :10;
    unsigned PeakCurrent  :2;
    unsigned Reserved  :3;
    unsigned DataRoleSwap  :1;
    unsigned UsbCommunicationCapable  :1;
    unsigned ExternallyPowered  :1;
    unsigned UsbSuspendSupported  :1;
    unsigned DualRolePower  :1;
    unsigned FixedSupply  :2;
  } FixedSupplyPdo;
  struct {
    unsigned MaximumCurrentIn10mA  :10;
    unsigned MinimumVoltageIn50mV  :10;
    unsigned MaximumVoltageIn50mV  :10;
    unsigned VariableSupportNonBattery  :2;
  } VariableSupplyNonBatteryPdo;
  struct {
    unsigned MaximumAllowablePowerIn250mW  :10;
    unsigned MinimumVoltageIn50mV  :10;
    unsigned MaximumVoltageIn50mV  :10;
    unsigned Battery  :2;
  } BatterySupplyPdo;
} UCM_PD_POWER_DATA_OBJECT, *PUCM_PD_POWER_DATA_OBJECT;
````


## -struct-fields

### -field Ul

Size of the structure.


### -field Common


### -field Reserved

Reserved.


### -field Type

Type of Power Data Object.

</dd>
</dl>

### -field FixedSupplyPdo

Describing a Fixed Supply type Power Data Object.


### -field MaximumCurrentIn10mA

Maximum current in multiples of 10 mA.


### -field VoltageIn50mV

Voltage in multiples of 50 mV.


### -field PeakCurrent

Peak current.


### -field Reserved

Reserved for future use.


### -field DataRoleSwap

If set, indicates the Power Data Object can perform a data role swap.


### -field UsbCommunicationCapable

If set, indicates the Power Data Object is USB communication capable. 


### -field ExternallyPowered

If set, indicates the Power Data Object is externally powered.


### -field UsbSuspendSupported

Indicates support for USB suspend.




### -field DualRolePower

Dual role power


### -field FixedSupply

fixed supply

</dd>
</dl>

### -field VariableSupplyNonBatteryPdo

Contains bitfields describing a variable-supply non-battery PD object.


### -field MaximumCurrentIn10mA

Describes the maximum current in multiples of 10 mA.


### -field MinimumVoltageIn50mV

Desribes the minimum voltage in multiples of 50 mV.


### -field MaximumVoltageIn50mV

Describes the maximum voltage in multiples of 50 mV.


### -field VariableSupportNonBattery

Variable Support Non Battery type.

</dd>
</dl>

### -field BatterySupplyPdo

Contains bitfields describing a battery supply PD object.


### -field MaximumAllowablePowerIn250mW

Describes the maximum allowable power in multiples of 250 mW.


### -field MinimumVoltageIn50mV

Describes the minimum voltage in multiples of 50 mV.


### -field MaximumVoltageIn50mV

Describes the maximum voltage in multiples of 50 mV.


### -field Battery

Battery type.

</dd>
</dl>

## -remarks
