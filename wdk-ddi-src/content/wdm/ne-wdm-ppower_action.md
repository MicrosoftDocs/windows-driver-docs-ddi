---
UID: NE:wdm.__unnamed_enum_0
title: POWER_ACTION
description: The POWER_ACTION enumeration identifies the system power actions that can occur on a computer.
tech.root: kernel
ms.date: 09/15/2020
keywords: ["POWER_ACTION enumeration"]
ms.keywords: POWER_ACTION, POWER_ACTION enumeration, PPOWER_ACTION, PPOWER_ACTION enumeration pointer, PowerActionHibernate, PowerActionNone, PowerActionReserved, PowerActionShutdown, PowerActionShutdownOff, PowerActionShutdownReset, PowerActionSleep, PowerActionWarmEject
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: POWER_ACTION
req.product: Windows 10 or later.
f1_keywords:
 - PPOWER_ACTION
 - wdm/PPOWER_ACTION
 - POWER_ACTION
 - wdm/POWER_ACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - PPOWER_ACTION
 - POWER_ACTION
---

# POWER_ACTION enumeration (wdm.h)


## -description

The <b>POWER_ACTION</b> enumeration identifies the <a href="/windows-hardware/drivers/kernel/system-power-actions">system power actions</a> that can occur on a computer.

## -enum-fields

### -field PowerActionNone

No power action is taking place.

### -field PowerActionReserved

Reserved for system use.

### -field PowerActionSleep

The computer is entering a <a href="/windows-hardware/drivers/kernel/system-sleeping-states">system sleeping (S1, S2, or S3) state</a>.

### -field PowerActionHibernate

The computer is entering its <a href="/windows-hardware/drivers/kernel/system-sleeping-states">hibernation (S4) state</a>.

### -field PowerActionShutdown

The computer is entering its <a href="/windows-hardware/drivers/kernel/system-shutdown-state-s5">shutdown (S5) state</a>. After all devices have entered their <a href="/windows-hardware/drivers/kernel/device-sleeping-states">off (D3) state</a>, the computer remains powered on until an administrator presses the power button.

### -field PowerActionShutdownReset

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off and then immediately restarts and returns to its working (S0) state.

### -field PowerActionShutdownOff

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off.

### -field PowerActionWarmEject

The computer is being ejected from an ACPI-compatible dock device. Typically, the computer's power state does not change.

### -field PowerActionDisplayOff

## -remarks

