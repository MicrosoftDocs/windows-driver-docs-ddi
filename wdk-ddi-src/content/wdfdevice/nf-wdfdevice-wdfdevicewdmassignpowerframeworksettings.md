---
UID: NF:wdfdevice.WdfDeviceWdmAssignPowerFrameworkSettings
title: WdfDeviceWdmAssignPowerFrameworkSettings function (wdfdevice.h)
description: The WdfDeviceWdmAssignPowerFrameworkSettings method registers power management framework (PoFx) settings for single-component devices.
old-location: wdf\wdfdevicewdmassignpowerframeworksettings.htm
tech.root: wdf
ms.assetid: 676A458E-A6E0-4F09-AAF2-21EA122EF74D
ms.date: 02/26/2018
keywords: ["WdfDeviceWdmAssignPowerFrameworkSettings function"]
ms.keywords: WdfDeviceWdmAssignPowerFrameworkSettings, WdfDeviceWdmAssignPowerFrameworkSettings method, kmdf.wdfdevicewdmassignpowerframeworksettings, wdf.wdfdevicewdmassignpowerframeworksettings, wdfdevice/WdfDeviceWdmAssignPowerFrameworkSettings
f1_keywords:
 - "wdfdevice/WdfDeviceWdmAssignPowerFrameworkSettings"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceWdmAssignPowerFrameworkSettings
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceWdmAssignPowerFrameworkSettings function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method registers  power management framework (PoFx) settings for single-component devices.


## -parameters




### -param Device [in]

A handle to the framework device object for which PoFx settings are being specified.


### -param PowerFrameworkSettings [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_framework_settings">WDF_POWER_FRAMEWORK_SETTINGS</a> structure that describes the client driver’s PoFx settings.


## -returns



The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method returns an NTSTATUS value that indicates success or failure of the operation.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_wake_settings">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure is incorrect. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The calling driver is not the device's power policy owner.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid <i>Settings</i> value is detected.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method applies only to single-component devices.

After calling this method, the client driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a> and set the <b>IdleTimeoutType</b> field of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure to <b>SystemManagedIdleTimeout</b> or <b>SystemManagedIdleTimeoutWithHint</b>.

A driver must call <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> before or during the first time a device starts. Because a device can start more than once, for example if resource rebalancing occurs, a driver might call this method from within <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>  or  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>. The framework calls these functions only once, even if the device is started more than once.

Alternatively, the driver could keep track of whether it has already called <b>WdfDeviceWdmAssignPowerFrameworkSettings</b>, and call it from one of the following callback functions: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled">EvtDeviceD0EntryPostInterruptsEnabled</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a>.

If your driver calls <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> more than once, the framework generates a verifier error.

The power management framework (PoFx) is available only on Windows 8 and later. When running on an operating system that does not support PoFx, <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> takes no action and returns STATUS_SUCCESS.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-functional-power-states">Supporting Functional Power States</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Overview of the Power Management Framework</a>.


#### Examples

In the following code example, the driver initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_framework_settings">WDF_POWER_FRAMEWORK_SETTINGS</a> structure by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_power_framework_settings_init">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>  function. The driver then manually sets some of the members of the structure, and then calls <b>WdfDeviceWdmAssignPowerFrameworkSettings</b>.

```cpp
NTSTATUS status;
WDF_POWER_FRAMEWORK_SETTINGS poFxSettings;

WDF_POWER_FRAMEWORK_SETTINGS_INIT(&poFxSettings);

poFxSettings.EvtDeviceWdmPostPoFxRegisterDevice = 
                        SingleCompWdmEvtDeviceWdmPostPoFxRegisterDevice;
poFxSettings.EvtDeviceWdmPrePoFxUnregisterDevice =
                        SingleCompWdmEvtDeviceWdmPrePoFxUnregisterDevice;

poFxSettings.Component = &component;
poFxSettings.ComponentIdleStateCallback = 
                        SingleCompWdmIdleStateCallback;
poFxSettings.PoFxDeviceContext = (PVOID) Device;
    
status = WdfDeviceWdmAssignPowerFrameworkSettings(Device, &poFxSettings);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device">EvtDeviceWdmPrePoFxUnregisterDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_framework_settings">WDF_POWER_FRAMEWORK_SETTINGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_power_framework_settings_init">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>
 

 

