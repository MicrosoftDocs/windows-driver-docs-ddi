---
UID: NE:storport._STOR_DEVICE_POWER_STATE
tech.root: storage
title: STOR_DEVICE_POWER_STATE
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The STOR_DEVICE_POWER_STATE enumeration identifies the power actions that can occur on a unit.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_DEVICE_POWER_STATE
 - PSTOR_DEVICE_POWER_STATE
 - STOR_DEVICE_POWER_STATE
f1_keywords:
 - _STOR_DEVICE_POWER_STATE
 - storport/_STOR_DEVICE_POWER_STATE
 - PSTOR_DEVICE_POWER_STATE
 - storport/PSTOR_DEVICE_POWER_STATE
 - STOR_DEVICE_POWER_STATE
 - storport/STOR_DEVICE_POWER_STATE
dev_langs:
 - c++
---

## -description

The **STOR_DEVICE_POWER_STATE** enumeration identifies a storage [device power state](/windows-hardware/drivers/kernel/device-power-states).

## -enum-fields

### -field StorPowerDeviceUnspecified

Indicates an unspecified device power state.

### -field StorPowerDeviceD0

Indicates a maximum device power state, which corresponds to [device working state D0](/drivers/kernel/device-working-state-d0).

### -field StorPowerDeviceD1

Indicates a [device sleeping state](/drivers/kernel/device-sleeping-states) less than **StorPowerDeviceD0** and greater than **StorPowerDeviceD2**, which corresponds to device power state D1.

### -field StorPowerDeviceD2

Indicates a device sleeping state less than **StorPowerDeviceD1** and greater than **StorPowerDeviceD3**, which corresponds to device power state D2.

### -field StorPowerDeviceD3

Indicates the lowest-powered device sleeping state, which corresponds to device power state D3.

### -field StorPowerDeviceMaximum

The number of device power state values for this enumeration type that represent actual power states. The value of the other device power states is less than this value.

## -remarks

**STOR_DEVICE_POWER_STATE** is set in a
[**STOR_UNIT_CONTROL_POWER**](ns-storport-stor_unit_control_power.md) structure.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_UNIT_CONTROL_POWER**](ns-storport-stor_unit_control_power.md)
