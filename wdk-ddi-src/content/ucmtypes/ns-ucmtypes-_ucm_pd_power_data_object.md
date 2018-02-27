---
UID: NS:ucmtypes._UCM_PD_POWER_DATA_OBJECT
title: "_UCM_PD_POWER_DATA_OBJECT"
author: windows-driver-content
description: Describes a Power Data Object. For information about these members, see the Power Delivery specification.
old-location: buses\ucm_pd_power_data_object.htm
old-project: usbref
ms.assetid: C54750A9-EE64-4FE7-9ED6-EC9709A82C43
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucmtypes.h
apiname:
-	UCM_PD_POWER_DATA_OBJECT
product: Windows
targetos: Windows
req.typenames: UCM_PD_POWER_DATA_OBJECT, *PUCM_PD_POWER_DATA_OBJECT
req.product: Windows 10 or later.
---

# _UCM_PD_POWER_DATA_OBJECT structure


## -description


Describes a Power Data Object. For information about these members, see the <a href="http://www.usb.org/developers/docs/usb20_docs/">Power Delivery specification</a>.


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



#### Reserved

Reserved.



#### Type

Type of Power Data Object.


### -field FixedSupplyPdo

Describing a Fixed Supply type Power Data Object.



#### MaximumCurrentIn10mA

Maximum current in multiples of 10 mA.



#### VoltageIn50mV

Voltage in multiples of 50 mV.



#### PeakCurrent

Peak current.



#### Reserved

Reserved for future use.



#### DataRoleSwap

If set, indicates the Power Data Object can perform a data role swap.



#### UsbCommunicationCapable

If set, indicates the Power Data Object is USB communication capable. 



#### ExternallyPowered

If set, indicates the Power Data Object is externally powered.



#### UsbSuspendSupported

Indicates support for USB suspend.





#### DualRolePower

Dual role power



#### FixedSupply

fixed supply


### -field VariableSupplyNonBatteryPdo

Contains bitfields describing a variable-supply non-battery PD object.



#### MaximumCurrentIn10mA

Describes the maximum current in multiples of 10 mA.



#### MinimumVoltageIn50mV

Desribes the minimum voltage in multiples of 50 mV.



#### MaximumVoltageIn50mV

Describes the maximum voltage in multiples of 50 mV.



#### VariableSupportNonBattery

Variable Support Non Battery type.


### -field BatterySupplyPdo

Contains bitfields describing a battery supply PD object.



#### MaximumAllowablePowerIn250mW

Describes the maximum allowable power in multiples of 250 mW.



#### MinimumVoltageIn50mV

Describes the minimum voltage in multiples of 50 mV.



#### MaximumVoltageIn50mV

Describes the maximum voltage in multiples of 50 mV.



#### Battery

Battery type.

