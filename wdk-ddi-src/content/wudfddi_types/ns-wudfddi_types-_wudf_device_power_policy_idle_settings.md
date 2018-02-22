---
UID: NS:wudfddi_types._WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
title: "_WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS"
author: windows-driver-content
description: The WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure contains driver-supplied information that the framework uses when a device is idle and the system is in the system working state (S0).
old-location: wdf\wudf_device_power_policy_idle_settings.htm
old-project: wdf
ms.assetid: E6EF8852-E39C-491B-9430-0308CA6276C0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: umdf.wudf_device_power_policy_idle_settings, wdf.wudf_device_power_policy_idle_settings, PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, *PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, wudfddi_types/PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, wudfddi_types/WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure, _WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure pointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfddi_types.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wudfddi_types.h
apiname:
-	WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
product: Windows
targetos: Windows
req.typenames: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, *PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS
req.product: Windows 10 or later.
---

# _WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure contains driver-supplied information that the framework uses when a device is idle and the system is in the system working state (S0).


## -syntax


````
typedef struct _WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS {
  ULONG                                  Size;
  WDF_POWER_POLICY_S0_IDLE_CAPABILITIES  IdleCaps;
  DEVICE_POWER_STATE                     DxState;
  ULONG                                  IdleTimeout;
  WDF_POWER_POLICY_S0_IDLE_USER_CONTROL  UserControlOfIdleSettings;
  WDF_TRI_STATE                          Enabled;
  WDF_TRI_STATE                          PowerUpIdleDeviceOnSystemWake;
  WDF_TRI_STATE                          ExcludeD3Cold;
} WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS, *PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field IdleCaps

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities.md">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator that identifies the device's ability to wake itself up after being set to a low-power state, while the system remains in its working (S0) state.


### -field DxState

A DEVICE_POWER_STATE-typed enumerator that identifies the low <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a> that the device will enter after the idle timeout period ends. DEVICE_POWER_STATE values are defined in <i>wdm.h</i>.


### -field IdleTimeout

The amount of time, in milliseconds, that the device will remain idle before the framework places it in the <b>DxState</b>-supplied low-power state. To use the framework's default idle timeout value, specify <b>IdleTimeoutDefaultValue</b>. For more information on when the framework considers the device to be idle, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.


### -field UserControlOfIdleSettings

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_power_policy_s0_idle_user_control.md">WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</a>-typed enumerator that indicates whether users have the ability to modify the device's idle settings.


### -field Enabled

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device will be powered down if it remains idle and while the system power is at S0. This member can have one of the following values:

<b>WdfTrue</b> - Powering down is enabled.

<b>WdfFalse</b> - Powering down is disabled.

<b>WdfUseDefault</b> - Powering down is initially enabled by default; but if the <b>UserControlOfIdleSettings</b> member is set to <b>IdleAllowUserControl</b>, the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior-in-umdf">user's setting or driver's INF file</a> overrides the initial value.

If powering down is enabled, the device has a wake-up capability, and the idle timeout value expires, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556817">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a> method before the device enters a low-power state.


### -field PowerUpIdleDeviceOnSystemWake

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device will return to its working (D0) state when the system returns to its working (S0) state. This member is valid only if the driver sets the <b>IdleCaps</b> member to <a href="..\wdfdevice\ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities.md">IdleCannotWakeFromS0</a>. The <b>PowerUpIdleDeviceOnSystemWake</b> member can have one of the following values:

<b>WdfTrue</b> - If both the device and the system are in a low-power state, the device returns to its working state when the system returns to its working state.

<b>WdfFalse</b> - If both the device and the system are in a low-power state, the device remains in the low-power state when the system returns to its working state.

<b>WdfUseDefault</b> - The default value that the framework uses if the driver does not set a different value. This value has the same meaning as <b>WdfFalse</b>. 

If the <b>PowerUpIdleDeviceOnSystemWake</b> member is set to <b>WdfFalse</b> or <b>WdfUseDefault</b>, the device returns to its working state only when software accesses the device, such as when an application sends an I/O request to the device. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">A Device Returns to Its Working State</a>.


### -field ExcludeD3Cold

A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed enumerator that indicates whether the framework can put the device in the D3cold power state when the idle timeout period expires. The <b>ExcludeD3Cold</b> member can have one of the following values:

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

The <b>ExcludeD3Cold</b> member is available starting in UMDF version 1.11, and is ignored in operating systems earlier than Windows 8. See additional information in Remarks.


## -remarks



The <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure is used as input to <a href="https://msdn.microsoft.com/D020B8AA-7353-47E1-A111-82BFE6F5F03D">IWDFDevice3::AssignS0IdleSettingsEx</a>. 

The first time a driver calls <a href="https://msdn.microsoft.com/D020B8AA-7353-47E1-A111-82BFE6F5F03D">IWDFDevice3::AssignS0IdleSettingsEx</a>, the following actions occur:

<ul>
<li>
The framework stores the values of all <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure members. 

</li>
<li>
If the <b>UserControlOfIdleSettings</b> member is set to <b>IdleAllowUserControl</b> and if the <b>Enabled</b> member is set to <b>WdfUseDefault</b>, the framework reads the registry to find out if the user has enabled powering down the device when it is idle.

</li>
</ul>
During subsequent calls to <a href="https://msdn.microsoft.com/D020B8AA-7353-47E1-A111-82BFE6F5F03D">IWDFDevice3::AssignS0IdleSettingsEx</a>, the framework only stores the values of the <b>DxState</b>, <b>IdleTimeout</b>, and <b>Enabled</b> members. Also, the framework stores the value of the <b>IdleCaps</b> member subject to the following rules:


<ul>
<li>
If the driver has ever specified <b>IdleCanWakeFromS0</b> for the <i>IdleCaps</i> parameter's value in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451202">AssignS0IdleSettingsEx</a>, it cannot subsequently change that value to <b>IdleUsbSelectiveSuspend</b>.

</li>
<li>
If the driver has ever specified <b>IdleUsbSelectiveSuspend</b> for the <i>IdleCaps</i> parameter's value in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451202">AssignS0IdleSettingsEx</a>, it cannot subsequently change that value to <b>IdleCanWakeFromS0</b>.

</li>
</ul>


The following rules apply to the value that you specify for the <b>DxState</b> member:

<ul>
<li>
The value cannot be <b>PowerDeviceD0</b>.

</li>
<li>
For USB devices, the value cannot be <b>PowerDeviceD0</b> or <b>PowerDeviceD3</b>.

</li>
<li>
If you specify <b>DevicePowerMaximum</b>, the framework uses the value that the driver for the device's bus supplied in the <b>DeviceWake</b> member of its <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure.

</li>
<li>
If the value of the <b>IdleCaps</b> member is <b>IdleCanWakeFromS0</b>, you cannot specify a device power state that is lower than the device power state in the <b>DeviceWake</b> member of the bus driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure. (In other words, if the bus driver's <b>DeviceWake</b> value is <b>PowerDeviceD2</b>, your function driver's <b>DxState</b> value cannot be <b>PowerDeviceD3</b>.)

</li>
</ul>
In operating systems earlier than Windows 8, the D3 power state signifies that the device is in a low-power state, but that some power to the bus is still maintained. Starting in Windows 8, the former D3 power state is called D3hot, and a new power state (D3cold) is available. A device can enter the D3cold state either while the system is in its working (S0) state or in a low-power state.  When a device is in the D3cold  power state, the bus is inactive and the device must trigger its own wake signal when an external action (for example plugging in a network cable) causes a hardware event.

A device that <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">supports idle power-down</a> can use the <b>ExcludeD3Cold</b> member of this structure to specify whether the D3cold power state should be an allowable choice for the low <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a> that the device will enter after the idle timeout period ends.

For information about registry entries that control a device's idle capabilities, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior-in-umdf">User Control of Device Idle and Wake Behavior in UMDF</a>. 

To initialize its <b>WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</b> structure, your driver should call <a href="..\wudfdevice\nf-wudfdevice-wudf_device_power_policy_idle_settings_init.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</a>.




## -see-also

<a href="https://msdn.microsoft.com/D020B8AA-7353-47E1-A111-82BFE6F5F03D">IWDFDevice3::AssignS0IdleSettingsEx</a>



<a href="..\wudfdevice\nf-wudfdevice-wudf_device_power_policy_idle_settings_init.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

