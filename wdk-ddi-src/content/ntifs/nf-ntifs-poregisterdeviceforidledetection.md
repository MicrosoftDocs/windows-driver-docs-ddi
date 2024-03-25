---
UID: NF:ntifs.PoRegisterDeviceForIdleDetection
title: PoRegisterDeviceForIdleDetection function (ntifs.h)
description: Learn more about the PoRegisterDeviceForIdleDetection routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["PoRegisterDeviceForIdleDetection function"]
ms.keywords: PoRegisterDeviceForIdleDetection, PoRegisterDeviceForIdleDetection routine [Kernel-Mode Driver Architecture], kernel.poregisterdeviceforidledetection, portn_be0ccb17-9465-4f61-a8ed-fa945f5340d6.xml, wdm/PoRegisterDeviceForIdleDetection
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PoRegisterDeviceForIdleDetection
 - ntifs/PoRegisterDeviceForIdleDetection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoRegisterDeviceForIdleDetection
---

# PoRegisterDeviceForIdleDetection function (ntifs.h)

## -description

The **PoRegisterDeviceForIdleDetection** routine enables or cancels idle detection and sets idle time-out values for a device.

## -parameters

### -param DeviceObject [in]

A pointer to the driver-created [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md) for the device. This parameter can point to a physical device object (PDO) or a functional device object (FDO).

### -param ConservationIdleTime [in]

Sets the time-out value (in seconds) to apply when the system power policy optimizes for energy conservation. Specify zero to disable idle detection when conservation policy is in effect.

### -param PerformanceIdleTime [in]

Sets the time-out value (in seconds) to apply when the system power policy optimizes for performance. Specify zero to disable idle detection when performance policy is in effect.

### -param State [in]

Specifies the [device power state](/windows-hardware/drivers/kernel/device-power-states) to be requested in an [**IRP_MN_SET_POWER**](/windows-hardware/drivers/kernel/irp-mn-set-power) request when either **ConservationIdleTime** or **PerformanceIdleTime** has been met. Possible values are the [**DEVICE_POWER_STATE**](../wudfddi/ne-wudfddi-_device_power_state.md) values.

## -returns

**PoRegisterDeviceForIdleDetection** returns a pointer to the idle counter to indicate that idle detection has been enabled. It returns NULL to indicate that idle detection has been disabled, that an idle counter could not be allocated, or that one or both of the time-out values were invalid.

## -remarks

**PoRegisterDeviceForIdleDetection** enables drivers to use the idle detection mechanism provided by the [power manager](/windows-hardware/drivers/kernel/power-manager). Drivers call **PoRegisterDeviceForIdleDetection** for any of the following reasons:

* To enable idle detection for the device and set initial idle time-out values.
* To change the idle time-out values for a device.
* To disable idle detection for a device.

After enabling a device for idle detection, a driver calls [**PoSetDeviceBusy**](../wdm/nf-wdm-posetdevicebusy.md) whenever the device is in use, passing the non-NULL idle pointer returned by **PoRegisterDeviceForIdleDetection**. Calling **PoSetDeviceBusy** restarts the idle countdown. Note that a driver must not pass a NULL pointer to **PoSetDeviceBusy**.

Whenever the device satisfies the current idle time-out value, the power manager sends an **IRP_MN_SET_POWER** request to the top of the device stack, specifying device power state **State**. In response to the [**IRP**](../wdm/ns-wdm-_irp.md), each driver performs any device-specific tasks required before the power state transition, then passes the IRP to the next-lower driver. When the IRP reaches the bus driver, that driver puts the device in the requested lower power state and completes the IRP.

**PoRegisterDeviceForIdleDetection** sets time-out values for both conservation and performance. The **ConservationIdleTime** value applies when the system power policy optimizes for conservation; the **PerformanceIdleTime** value applies when the system power policy optimizes for performance. Typically, the applicable policy depends upon the power source: when running with AC power, the system optimizes for performance, and when running off a battery, the system optimizes for conservation.

Certain devices can specify time-out values of -1 to use the standard power policy time-outs for their device class. The standard time-out values provide for better system integration for supported standard device classes. At present, WDM supports this feature for devices of type FILE_DEVICE_DISK and FILE_DEVICE_MASS_STORAGE. **PoRegisterDeviceForIdleDetection** returns NULL if -1 is specified for a device of an unsupported type. For information about device types, see [Specifying Device Types](/windows-hardware/drivers/kernel/specifying-device-types).

Only one idle detection can be set per device. Subsequent calls to **PoRegisterDeviceForIdleDetection** change the idle detection values.

If both **ConservationIdleTime** and **PerformanceIdleTime** are zero, this routine cancels all idle detection for the device and returns NULL.

**PoRegisterDeviceForIdleDetection** can free a driver from the need to perform its own idle detection. However, drivers can also implement their own idle detection.

## -see-also

[**IRP**](../wdm/ns-wdm-_irp.md)

[**IRP_MN_SET_POWER**](/windows-hardware/drivers/kernel/irp-mn-set-power)

[**PoSetDeviceBusy**](../wdm/nf-wdm-posetdevicebusy.md)
