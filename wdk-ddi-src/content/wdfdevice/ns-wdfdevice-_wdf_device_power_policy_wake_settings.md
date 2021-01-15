---
UID: NS:wdfdevice._WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
title: _WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS (wdfdevice.h)
description: The WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure contains driver-supplied information about a device's ability to wake itself and the system, when both are in a low-power state.
old-location: wdf\wdf_device_power_policy_wake_settings.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure"]
ms.keywords: "*PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS, DFDeviceObjectGeneralRef_08482cf6-3f3d-44d2-b0f3-4856a23d94d0.xml, PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS, PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure pointer, WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS, WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure, _WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS, kmdf.wdf_device_power_policy_wake_settings, wdf.wdf_device_power_policy_wake_settings, wdfdevice/PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS, wdfdevice/WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS"
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
req.typenames: WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS, *PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
f1_keywords:
 - _WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
 - wdfdevice/_WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
 - PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
 - wdfdevice/PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
 - WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
 - wdfdevice/WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - _WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
 - PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
 - WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS
---

# _WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</b> structure contains driver-supplied information about a device's ability to wake itself and the system, when both are in a low-power state.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field DxState

A <a href="/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>-typed enumerator that identifies the low <a href="/windows-hardware/drivers/kernel/device-power-states">device power state</a> that the device will enter when the system power state drops to a wakeable low-power state. The value of <b>DxState</b> cannot be <b>PowerDeviceD0</b>. <b>DEVICE_POWER_STATE</b> values are defined in <i>wdm.h</i>.

### -field UserControlOfWakeSettings

A <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_sx_wake_user_control">WDF_POWER_POLICY_SX_WAKE_USER_CONTROL</a>-typed enumerator that indicates whether users have the ability to modify the device's wake settings.

### -field Enabled

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device can wake the system (that is, restore the system to S0) when the system is in a low-power state. This member can have one of the following values:

<b>WdfTrue</b> - Waking the system is enabled.

<b>WdfFalse</b> - Waking the system is disabled.

<b>WdfUseDefault</b> - Waking the system is initially enabled by default; but if the <b>UserControlOfWakeSettings</b> member is set to <b>WakeAllowUserControl</b>, the <a href="/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">user's setting or driver's INF file</a> overrides the initial value.

If waking the system is enabled and the system is about to enter a low-power state, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx">EvtDeviceArmWakeFromSx</a> or <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a> callback function before the device enters a low-power state.

### -field ArmForWakeIfChildrenAreArmedForWake

A Boolean value that, if set to <b>TRUE</b>, indicates that a parent device's ability to wake itself and the system should be enabled when this ability is enabled for the device's child devices. For more information, see the following Remarks section. This member is available in version 1.7 and later versions of KMDF.

### -field IndicateChildWakeOnParentWake

A Boolean value that, if set to <b>TRUE</b>, indicates that the framework will provide wake-up status to child devices if a parent device detects a wake-up signal. For more information, see the following Remarks section. This member is available in version 1.7 and later versions of KMDF.

## -remarks

The <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</b> structure is used as input to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignsxwakesettings">WdfDeviceAssignSxWakeSettings</a>. 

To initialize its <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</b> structure, your driver should call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_power_policy_wake_settings_init">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</a>.

The first time a driver calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignsxwakesettings">WdfDeviceAssignSxWakeSettings</a>, the following actions occur:

<ul>
<li>
The framework stores the values of all <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</b> structure members. 

</li>
<li>
If the <b>UserControlOfWakeSettings</b> member is set to <b>WakeAllowUserControl</b> and if the <b>Enabled</b> member is set to <b>WdfUseDefault</b>, the framework reads the registry to find out if the user has enabled waking the system.

</li>
</ul>
During subsequent calls to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignsxwakesettings">WdfDeviceAssignSxWakeSettings</a>, the framework does not store the value of the <b>UserControlOfWakeSettings</b>  member. In other words, the framework performs the following steps the first time the driver calls <b>WdfDeviceAssignSxWakeSettings</b> but not during later calls:

<ul>
<li>
Stores the value of the <b>UserControlOfWakeSettings</b> member. 

</li>
<li>
Looks for a user setting in the registry, if the value of the <b>Enabled</b> member is <b>WdfUseDefault</b>.

</li>
</ul>
The following rules apply to the value that you specify for the <b>DxState</b> member:

<ul>
<li>
The value cannot be <b>PowerDeviceD0</b>.

</li>
<li>
If you specify <b>PowerDeviceMaximum</b>, the framework uses the value that the driver for the device's bus supplied in the <b>DeviceWake</b> member of its <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure.

</li>
<li>
You cannot specify a device power state that is lower than the device power state in the <b>DeviceWake</b> member of the bus driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure. (In other words, if the bus driver's <b>DeviceWake</b> value is <b>PowerDeviceD2</b>, your function driver's <b>DxState</b> value cannot be <b>PowerDeviceD3</b>.)

</li>
</ul>
For information about registry entries that control a device's wake capabilities, see <a href="/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">User Control of Device Idle and Wake Behavior</a>. 

If the device that the <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</b> structure describes is a parent device, the driver for the parent device can use the <b>ArmForWakeIfChildrenAreArmedForWake</b> and <b>IndicateChildWakeOnParentWake</b> members as follows:

<ul>
<li>
If the driver sets the <b>ArmForWakeIfChildrenAreArmedForWake</b> member to <b>TRUE</b>, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx">EvtDeviceArmWakeFromSx</a> or <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a> callback function when a child device's wake ability is enabled, even if the parent device's wake ability is not enabled.

To reduce power consumption, you might not want to enable your device's wake ability unless a child device that also supports a wake ability is plugged in. If your driver sets the <b>ArmForWakeIfChildrenAreArmedForWake</b> member to <b>TRUE</b>, the <b>Enabled</b> member's values have the following meanings:

<ul>
<li>If <b>Enabled</b> is <b>WdfFalse</b>, the framework enables your driver's wake ability only if a child device's wake ability is enabled.</li>
<li>If <b>Enabled</b> is <b>WdfTrue</b>, the framework always enables your driver's wake ability, whether your device has wake-enabled child devices or not.</li>
<li>If <b>Enabled</b> is <b>WdfUseDefault</b> and <b>UserControlOfWakeSettings</b> is <b>WakeAllowUserControl</b>, users can control whether your device is always wake-enabled or if it is wake-enabled only when your device has child devices that are wake-enabled.</li>
</ul>
</li>
<li>
If the driver sets the <b>IndicateChildWakeOnParentWake</b> member to <b>TRUE</b>, the framework calls the <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered">EvtDeviceWakeFromSxTriggered</a> callback function in the parent device's driver and in the driver for each wake-enabled child device. If the driver sets this member to <b>FALSE</b>, the framework calls the <i>EvtDeviceWakeFromSxTriggered</i> callback function in the parent device's driver only. Your driver should set <b>IndicateChildWakeOnParentWake</b> to <b>TRUE</b> if the drivers for your device's children must examine hardware to determine why the system was awakened.

</li>
</ul>
For more information about how to support a device's wake ability, see <a href="/windows-hardware/drivers/wdf/supporting-system-wake-up">Supporting System Wake-Up</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx">EvtDeviceArmWakeFromSx</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason">EvtDeviceArmWakeFromSxWithReason</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered">EvtDeviceWakeFromSxTriggered</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_power_policy_wake_settings_init">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_sx_wake_user_control">WDF_POWER_POLICY_SX_WAKE_USER_CONTROL</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassignsxwakesettings">WdfDeviceAssignSxWakeSettings</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceindicatewakestatus">WdfDeviceIndicateWakeStatus</a>

