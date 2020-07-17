---
UID: NF:ntifs.PoRegisterDeviceForIdleDetection
title: PoRegisterDeviceForIdleDetection function (ntifs.h)
description: The PoRegisterDeviceForIdleDetection routine enables or cancels idle detection and sets idle time-out values for a device.
old-location: kernel\poregisterdeviceforidledetection.htm
tech.root: kernel
ms.assetid: f786fa36-1faa-4e12-aec1-872b44c01a85
ms.date: 04/30/2018
keywords: ["PoRegisterDeviceForIdleDetection function"]
ms.keywords: PoRegisterDeviceForIdleDetection, PoRegisterDeviceForIdleDetection routine [Kernel-Mode Driver Architecture], kernel.poregisterdeviceforidledetection, portn_be0ccb17-9465-4f61-a8ed-fa945f5340d6.xml, wdm/PoRegisterDeviceForIdleDetection
f1_keywords:
 - "ntifs/PoRegisterDeviceForIdleDetection"
 - "PoRegisterDeviceForIdleDetection"
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoRegisterDeviceForIdleDetection
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoRegisterDeviceForIdleDetection function


## -description


The <b>PoRegisterDeviceForIdleDetection</b> routine enables or cancels idle detection and sets idle time-out values for a device.


## -parameters




### -param DeviceObject [in]

A pointer to the driver-created <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> for the device. On Windows 2000 and later systems, this parameter can point to a physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>) or a functional device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">FDO</a>). On Windows 98/Me, this parameter must point to the PDO of the underlying device.


### -param ConservationIdleTime [in]

Sets the time-out value (in seconds) to apply when the system power policy optimizes for energy conservation. Specify zero to disable idle detection when conservation policy is in effect.


### -param PerformanceIdleTime [in]

Sets the time-out value (in seconds) to apply when the system power policy optimizes for performance. Specify zero to disable idle detection when performance policy is in effect.


### -param State [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a> to be requested in an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a> request when either <i>ConservationIdleTime</i> or <i>PerformanceIdleTime</i> has been met. Possible values are the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a> values.


## -returns



<b>PoRegisterDeviceForIdleDetection</b> returns a pointer to the idle counter to indicate that idle detection has been enabled. It returns <b>NULL</b> to indicate that idle detection has been disabled, that an idle counter could not be allocated, or that one or both of the time-out values were invalid.




## -remarks



<b>PoRegisterDeviceForIdleDetection</b> enables drivers to use the idle detection mechanism provided by the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-manager">power manager</a>. Drivers call <b>PoRegisterDeviceForIdleDetection</b> for any of the following reasons:

<ul>
<li>
To enable idle detection for the device and set initial idle time-out values

</li>
<li>
To change the idle time-out values for a device

</li>
<li>
To disable idle detection for a device

</li>
</ul>
After enabling a device for idle detection, a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">PoSetDeviceBusy</a> whenever the device is in use, passing the non-<b>NULL</b> idle pointer returned by <b>PoRegisterDeviceForIdleDetection</b>. Calling <b>PoSetDeviceBusy</b> restarts the idle countdown. Note that a driver must not pass a <b>NULL</b> pointer to <b>PoSetDeviceBusy</b>.

Whenever the device satisfies the current idle time-out value, the power manager sends an <b>IRP_MN_SET_POWER</b> request to the top of the device stack, specifying device power state <i>State</i>. In response to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>, each driver performs any device-specific tasks required before the power state transition, then passes the IRP to the next-lower driver. When the IRP reaches the bus driver, that driver puts the device in the requested lower power state and completes the IRP.

<b>PoRegisterDeviceForIdleDetection</b> sets time-out values for both conservation and performance. The <i>ConservationIdleTime</i> value applies when the system power policy optimizes for conservation; the <i>PerformanceIdleTime</i> value applies when the system power policy optimizes for performance. Typically, the applicable policy depends upon the power source: when running with AC power, the system optimizes for performance, and when running off a battery, the system optimizes for conservation. 

Certain devices can specify time-out values of -1 to use the standard power policy time-outs for their device class. The standard time-out values provide for better system integration for supported standard device classes. At present, WDM supports this feature for devices of type FILE_DEVICE_DISK and FILE_DEVICE_MASS_STORAGE. <b>PoRegisterDeviceForIdleDetection</b> returns <b>NULL</b> if -1 is specified for a device of an unsupported type. (For information about device types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/specifying-device-types">Specifying Device Types</a>.)

Only one idle detection can be set per device. Subsequent calls to <b>PoRegisterDeviceForIdleDetection</b> change the idle detection values.

If both <i>ConservationIdleTime</i> and <i>PerformanceIdleTime</i> are zero, this routine cancels all idle detection for the device and returns <b>NULL</b>.

<b>PoRegisterDeviceForIdleDetection</b> can free a driver from the need to perform its own idle detection. However, drivers can also implement their own idle detection.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">PoSetDeviceBusy</a>
 

 

