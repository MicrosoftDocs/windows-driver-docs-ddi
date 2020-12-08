---
UID: NF:wdfdevice.WdfDeviceGetSystemPowerAction
title: WdfDeviceGetSystemPowerAction function (wdfdevice.h)
description: The WdfDeviceGetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer.
old-location: wdf\wdfdevicegetsystempoweraction.htm
tech.root: wdf
ms.date: 03/24/2020
keywords: ["WdfDeviceGetSystemPowerAction function"]
ms.keywords: DFDeviceObjectGeneralRef_605cddb8-470b-4d71-8a6e-295e060ea3e3.xml, WdfDeviceGetSystemPowerAction, WdfDeviceGetSystemPowerAction method, kmdf.wdfdevicegetsystempoweraction, wdf.wdfdevicegetsystempoweraction, wdfdevice/WdfDeviceGetSystemPowerAction
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceGetSystemPowerAction
 - wdfdevice/WdfDeviceGetSystemPowerAction
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfDeviceGetSystemPowerAction
---

# WdfDeviceGetSystemPowerAction function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceGetSystemPowerAction</b> method returns the <a href="/windows-hardware/drivers/kernel/system-power-actions">system power action</a>, if any, that is currently occurring for the computer.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -returns

<b>WdfDeviceGetSystemPowerAction</b> returns a POWER_ACTION-typed enumerator value. The value indicates the <a href="/windows-hardware/drivers/kernel/system-power-actions">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. The POWER_ACTION enumeration is defined in <i>wdm.h</i>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

Starting in WDF version 1.31/2.31 (referred to as "v31"), **WdfDeviceGetSystemPowerAction** has been updated to more accurately report system power action when the device is the power policy owner. Drivers need to be recompiled with v31 or later to get the following new behavior:

* If the device enters or exits D0 due to S0 Idle (see [**WdfDeviceAssignS0IdleSettings**](./nf-wdfdevice-wdfdeviceassigns0idlesettings.md)) while an unrelated system power transition is in progress, **WdfDeviceGetSystemPowerAction** might return **PowerActionSleep**. This is fixed in v31 and now it returns **PowerActionNone**.
* When the system wakes up from Hybrid Sleep (sleep with a hibernation file), before v31, **WdfDeviceGetSystemPowerAction** always returned **PowerActionHibernate**. This is fixed in v31 and now it returns:

   - **PowerActionSleep** if it wakes without power loss, which means the system remained in S3
   - **PowerActionHibernate** if it wakes after power loss, which means the system resumed from the hibernation file


The <b>WdfDeviceGetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. 

The driver must call <b>WdfDeviceGetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">entering a low-power state</a> or <a href="/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returning to its working state</a>. 

The value that <b>WdfDeviceGetSystemPowerAction</b> returns depends on the following situations:

<ul>
<li>
If the computer is entering a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer is entering the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is entering its S1, S2, or S3 low-power state.

</li>
<li>
If the computer is returning to its working (S0) state from a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer entered the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is leaving its S1, S2, or S3 low-power state.

</li>
<li>
If the computer is powering up (after having been turned off) when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

</li>
<li>
If the device is entering a low-power idle state or returning to its working (D0) state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, while the rest of the system remains at its working (S0) state, the method returns <b>PowerActionNone</b>.

</li>
<li>
If the computer and the device are both in their working states when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

</li>
</ul>
For more information about low-power states, see <a href="/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">A Device Enters a Low-Power State</a>.


#### Examples

The following code example obtains the power transition activity that is currently occurring for the computer.

```cpp
POWER_ACTION SysPowerAction;

SysPowerAction = WdfDeviceGetSystemPowerAction(device);
```
