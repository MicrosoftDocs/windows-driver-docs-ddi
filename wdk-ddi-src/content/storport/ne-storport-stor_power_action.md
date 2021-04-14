---
UID: NE:storport.__unnamed_enum_0
tech.root: storage
title: STOR_POWER_ACTION
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The STOR_POWER_ACTION enumeration identifies the system power actions that can occur on a computer.
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
 - PSTOR_POWER_ACTION
 - STOR_POWER_ACTION
f1_keywords:
 - PSTOR_POWER_ACTION
 - storport/PSTOR_POWER_ACTION
 - STOR_POWER_ACTION
 - storport/STOR_POWER_ACTION
dev_langs:
 - c++
---

## -description

The **STOR_POWER_ACTION** enumeration identifies the system power actions that can occur on a computer.

## -enum-fields

### -field StorPowerActionNone

No power action is taking place.

### -field StorPowerActionReserved

Reserved for system use.

### -field StorPowerActionSleep

The computer is entering a [system sleeping (S1, S2, or S3) state](/windows-hardware/drivers/kernel/system-sleeping-states).

### -field StorPowerActionHibernate

The computer is entering its [hibernation (S4) state](/windows-hardware/drivers/kernel/system-sleeping-states).

### -field StorPowerActionShutdown

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer remains powered on until an administrator presses the power button.

### -field StorPowerActionShutdownReset

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off and then immediately restarts and returns to its working (S0) state.

### -field StorPowerActionShutdownOff

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off.

### -field StorPowerActionWarmEject

The computer is being ejected from an ACPI-compatible dock device. Typically, the computer's power state does not change.

## -remarks

For a unit, Storport sets **STOR_POWER_ACTION** in the
[**STOR_UNIT_CONTROL_POWER**](ns-storport-stor_unit_control_power.md) structure.

For an adapter, Storport sets **STOR_POWER_ACTION** in the [**STOR_ADAPTER_CONTROL_POWER**](ns-storport-stor_adapter_control_power.md) structure.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)
