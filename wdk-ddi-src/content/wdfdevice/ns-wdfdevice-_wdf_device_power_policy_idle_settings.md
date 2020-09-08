---
UID: NS:wdfdevice._WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
title: _WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS (wdfdevice.h)
description: The WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure contains driver-supplied information that the framework uses when a device is idle and the system is in the system working state (S0).
old-location: wdf\wdf_device_power_policy_idle_settings.htm
tech.root: wdf
ms.assetid: 8d5acd3a-3ec3-4190-98d4-e7ce9ea8d3e8
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure"]
ms.keywords: "*PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, DFDeviceObjectGeneralRef_82f4a32c-ff51-4b0f-a67a-c45b4777ce23.xml, PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure pointer, WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure, _WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, kmdf.wdf_device_power_policy_idle_settings, wdf.wdf_device_power_policy_idle_settings, wdfdevice/PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, wdfdevice/WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, *PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
f1_keywords:
 - _WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
 - wdfdevice/_WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
 - PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
 - wdfdevice/PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
 - WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
 - wdfdevice/WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
---

# _WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure contains driver-supplied information that the framework uses when a device is idle and the system is in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0).

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field IdleCaps

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator that identifies the device's ability to wake itself up after being set to a low-power state, while the system remains in its working (S0) state.

### -field DxState

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>-typed enumerator that identifies the low <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a> that the device will enter after the idle timeout period ends. <b>DEVICE_POWER_STATE</b> values are defined in <i>wdm.h</i>.

### -field IdleTimeout

The amount of time, in milliseconds, that the device will remain idle before the framework places it in the <b>DxState</b>-supplied low-power state. To use the framework's default idle timeout value, specify <b>IdleTimeoutDefaultValue</b>. For more information on when the framework considers the device to be idle, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.

### -field UserControlOfIdleSettings

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_s0_idle_user_control">WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</a>-typed enumerator that indicates whether users have the ability to modify the device's idle settings.

### -field Enabled

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device will be powered down if it remains idle and while the system power is at S0. This member can have one of the following values:

<b>WdfTrue</b> - Powering down is enabled.

<b>WdfFalse</b> - Powering down is disabled.

<b>WdfUseDefault</b> - Powering down is initially enabled by default; but if the <b>UserControlOfIdleSettings</b> member is set to <b>IdleAllowUserControl</b>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">user's setting or driver's INF file</a> overrides the initial value.

If powering down is enabled, the device has a wake-up capability, and the idle timeout value expires, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0">EvtDeviceArmWakeFromS0</a> callback function before the device enters a low-power state.

### -field PowerUpIdleDeviceOnSystemWake

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device will return to its working (D0) state when the system returns to its working (S0) state. This member is valid only if the driver sets the <b>IdleCaps</b> member to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities">IdleCannotWakeFromS0</a>. The <b>PowerUpIdleDeviceOnSystemWake</b> member can have one of the following values:

<b>WdfTrue</b> - If both the device and the system are in a low-power state, the device returns to its working state when the system returns to its working state.

<b>WdfFalse</b> - If both the device and the system are in a low-power state, the device remains in the low-power state when the system returns to its working state.

<b>WdfUseDefault</b> - The default value that the framework uses if the driver does not set a different value. This value has the same meaning as <b>WdfFalse</b>. 

If the <b>PowerUpIdleDeviceOnSystemWake</b> member is set to <b>WdfFalse</b> or <b>WdfUseDefault</b>, the device returns to its working state only when software accesses the device, such as when an application sends an I/O request to the device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">A Device Returns to Its Working State</a>.

The <b>PowerUpIdleDeviceOnSystemWake</b> member is available in version 1.9 and later versions of KMDF, and starting in version 2.0 of UMDF.

### -field IdleTimeoutType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_idle_timeout_type">WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</a>-typed enumerator  that indicates how the <b>IdleTimeout</b> member is used.

The <b>IdleTimeoutType</b> member is available in version 1.11 and later versions of KMDF, and starting in version 2.0 of UMDF. See additional information in Remarks.

### -field ExcludeD3Cold

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed enumerator that indicates whether the D3cold power state should be an allowable choice for the low-power state that the device will enter when the idle timeout period expires. The <b>ExcludeD3Cold</b> member can have one of the following values:

<b>WdfTrue</b> - The framework will move a device to a low-power D-state when the idle timeout period expires.  If that D-state is D3, the device will be moved to D3hot.  If <b>ExcludeD3Cold</b> is set to <b>WdfTrue</b>, then no further transition from D3hot to D3cold will be allowed.

<b>WdfFalse</b> - The device may enter the D3cold power state when the idle timeout period expires, if all of the following criteria are met:

<ul>
<li>The <b>DxState</b> member of this structure specifies <b>PowerDeviceD3</b> or <b>PowerDeviceMaximum</b>.</li>
<li>The ACPI firmware indicates that the device supports the D3cold power state.</li>
<li>If the driver specified <b>IdleCanWakeFromS0</b> or <b>IdleUsbSelectiveSuspend</b> in the <b>IdleCaps</b> member of this structure, the device can respond to an external wake-up event while in the D3cold power state. Otherwise, this requirement does not apply.</li>
</ul>
<b>WdfUseDefault</b> - The framework examines the <i>DDInstall</i><b>.HW</b> section of the driver's INF file. If the following lines are present, this value has the same meaning as <b>WdfFalse</b>:<pre class="syntax" xml:space="preserve"><code>Include = machine.inf
Needs = PciD3ColdSupported
</code></pre> Otherwise, this value has the same meaning as <b>WdfTrue</b>.

The <b>ExcludeD3Cold</b> member is available starting in KMDF version 1.11, as well as starting in version 2.0 of UMDF, and is ignored in operating systems earlier than Windows 8. See additional information in Remarks.

## -remarks

The <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure is used as input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a>. 

The first time a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a>, the following actions occur:

<ul>
<li>
The framework stores the values of all <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure members. 

</li>
<li>
If the <b>UserControlOfIdleSettings</b> member is set to <b>IdleAllowUserControl</b> and if the <b>Enabled</b> member is set to <b>WdfUseDefault</b>, the framework reads the registry to find out if the user has enabled powering down the device when it is idle.

</li>
</ul>
During subsequent calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a>, the framework only stores the values of the <b>DxState</b>, <b>IdleTimeout</b>, and <b>Enabled</b> members. Also, in KMDF 1.9 and earlier, the framework stores the value of the <b>IdleCaps</b> member <i>unless</i> the value is <b>IdleUsbSelectiveSuspend</b>. Therefore, the driver must use the following rules:


<ul>
<li>
If the driver specifies <b>IdleUsbSelectiveSuspend</b> for the <b>IdleCaps</b> member's value, it must do so the first time that it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a>, and it cannot subsequently change that value.

</li>
<li>
	If the driver specifies <b>IdleCanWakeFromS0</b> or <b>IdleCannotWakeFromS0</b> the first time it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a>, it can subsequently call <b>WdfDeviceAssignS0IdleSettings</b> again to change that value (but it cannot change the value to <b>IdleUsbSelectiveSuspend</b>).


</li>
</ul>


Starting in KMDF 1.11 and UMDF 2.0, a KMDF driver can switch between <b>IdleUsbSelectiveSuspend</b> and <b>IdleCannotWakeFromS0</b> at any time.

Starting in Windows 8, setting the <b>IdleTimeoutType</b> member to <b>SystemManagedIdleTimeout</b> or <b>SystemManagedIdleTimeoutWithHint</b> causes the framework to register with the power management framework (PoFx).

If the driver is implementing functional power state support for a multiple-component device, the driver must either set <b>IdleTimeoutType</b> to <b>DriverManagedIdleTimeout</b> or not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a> at all.

 For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-functional-power-states">Supporting Functional Power States</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Overview of the Power Management Framework</a>.

The following rules apply to the value that you specify for the <b>DxState</b> member:

<ul>
<li>
The value cannot be <b>PowerDeviceD0</b>.

</li>
<li>
For USB devices, the value cannot be <b>PowerDeviceD0</b> or <b>PowerDeviceD3</b>.

</li>
<li>
If you specify <b>PowerDeviceMaximum</b>, the framework uses the value that the driver for the device's bus supplied in the <b>DeviceWake</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure.

</li>
<li>
If the value of the <b>IdleCaps</b> member is <b>IdleCanWakeFromS0</b>, you cannot specify a device power state that is lower than the device power state in the <b>DeviceWake</b> member of the bus driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure. (In other words, if the bus driver's <b>DeviceWake</b> value is <b>PowerDeviceD2</b>, your function driver's <b>DxState</b> value cannot be <b>PowerDeviceD3</b>.)

</li>
</ul>
In operating systems earlier than Windows 8, the D3 power state signifies that the device is in a low-power state, but that some power to the bus is still maintained. Starting in Windows 8, the former D3 power state is called D3hot, and a new power state (D3cold) is available. A device can enter the D3cold state either while the system is in its working (S0) state or in a low-power state.  When a device is in the D3cold  power state, the bus is inactive and the device must trigger its own wake signal when an external action (for example plugging in a network cable) causes a hardware event.

Starting in KMDF 1.11 and UMDF 2.0, a device that <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down">supports idle power-down</a> can use the <b>ExcludeD3Cold</b> member of this structure to specify whether the D3cold power state should be an allowable choice for the low <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a> that the device will enter after the idle timeout period ends.

For information about registry entries that control a device's idle capabilities, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">User Control of Device Idle and Wake Behavior</a>. 

To initialize its <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure, your driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_power_policy_idle_settings_init">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</a>.

