---
UID: NE:ntpoapi.__unnamed_enum_0
title: PPOWER_ACTION (ntpoapi.h)
description: The POWER_ACTION enumeration identifies the system power actions that can occur on a computer.
old-location: wdf\power_action.htm
tech.root: kernel
ms.date: 02/26/2018
keywords: ["*PPOWER_ACTION enumeration"]
ms.keywords: "*PPOWER_ACTION, POWER_ACTION, POWER_ACTION enumeration, PPOWER_ACTION, PPOWER_ACTION enumeration pointer, PowerActionHibernate, PowerActionNone, PowerActionReserved, PowerActionShutdown, PowerActionShutdownOff, PowerActionShutdownReset, PowerActionSleep, PowerActionWarmEject, umdf.power_action, umdfstructs_02db2a83-1907-4aa2-9cdd-af3477e78ddd.xml, wdf.power_action, wudfddi/POWER_ACTION, wudfddi/PPOWER_ACTION, wudfddi/PowerActionHibernate, wudfddi/PowerActionNone, wudfddi/PowerActionReserved, wudfddi/PowerActionShutdown, wudfddi/PowerActionShutdownOff, wudfddi/PowerActionShutdownReset, wudfddi/PowerActionSleep, wudfddi/PowerActionWarmEject"
req.header: ntpoapi.h
req.include-header: Wudfddi.h, Ntpoapi.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
f1_keywords:
 - PPOWER_ACTION
 - ntpoapi/PPOWER_ACTION
 - POWER_ACTION
 - ntpoapi/POWER_ACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi.h
api_name:
 - POWER_ACTION
---

# *PPOWER_ACTION enumeration (ntpoapi.h)


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

## -syntax

```cpp
typedef enum  {
  PowerActionNone           = 0,
  PowerActionReserved       = ( PowerActionNone + 1 ),
  PowerActionSleep          = ( PowerActionReserved + 1 ),
  PowerActionHibernate      = ( PowerActionSleep + 1 ),
  PowerActionShutdown       = ( PowerActionHibernate + 1 ),
  PowerActionShutdownReset  = ( PowerActionShutdown + 1 ),
  PowerActionShutdownOff    = ( PowerActionShutdownReset + 1 ),
  PowerActionWarmEject      = ( PowerActionShutdownOff + 1 )
} POWER_ACTION, *PPOWER_ACTION;
```

## -remarks

The <b>POWER_ACTION</b> enumeration is used as the return value for <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-getsystempoweraction">IWDFDevice2::GetSystemPowerAction</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-getsystempoweraction">IWDFDevice2::GetSystemPowerAction</a>
