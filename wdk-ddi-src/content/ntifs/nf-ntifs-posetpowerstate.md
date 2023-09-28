---
UID: NF:ntifs.PoSetPowerState
title: PoSetPowerState function (ntifs.h)
description: Learn more about the PoSetPowerState function.
tech.root: kernel
ms.date: 09/27/2023
keywords: ["PoSetPowerState function"]
ms.keywords: PoSetPowerState, PoSetPowerState routine [Kernel-Mode Driver Architecture], kernel.posetpowerstate, portn_b6d6559d-e4c7-4fa8-b0f2-556b840391f9.xml, wdm/PoSetPowerState
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - PoSetPowerState
 - ntifs/PoSetPowerState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoSetPowerState
---

# PoSetPowerState function (ntifs.h)

## -description

The **PoSetPowerState** routine notifies the system of a change in the [device power state](/windows-hardware/drivers/kernel/device-power-states) for a device.

## -parameters

### -param DeviceObject [in]

A pointer to the target [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md).

### -param Type [in]

Indicates a [**POWER_STATE_TYPE**](../wdm/ne-wdm-_power_state_type.md) value. Drivers must specify **DevicePowerState**.

### -param State [in]

Specifies the power state to be set. Drivers must specify a [**DEVICE_POWER_STATE**](../wudfddi/ne-wudfddi-_device_power_state.md) value.

## -returns

**PoSetPowerState** returns the previous power state.

## -remarks

**PoSetPowerState** notifies the [power manager](/windows-hardware/drivers/kernel/power-manager) of the new power state for a device. Each driver in a device stack (filter, function, and bus drivers) must call **PoSetPowerState** to inform the power manager of a change in the power state of its corresponding device object. For example:

* A driver calls this routine after receiving a device set-power request and before calling [**PoStartNextPowerIrp**](nf-ntifs-postartnextpowerirp.md). When handling a PnP [**IRP_MN_START_DEVICE**](/windows-hardware/drivers/kernel/irp-mn-start-device) request, the driver should call **PoSetPowerState** to notify the power manager that the device is in the D0 state.

* If the device is powering down, the driver must call **PoSetPowerState** before leaving the D0 state. In addition, the driver must be able to process client requests before **PoSetPowerState** returns.

* If the device is powering up, the driver must call **PoSetPowerState** after the device is successfully put into the D0 state.

For more information about powering a device up and down, see [Handling IRP_MN_SET_POWER for Device Power States](/windows-hardware/drivers/kernel/handling-irp-mn-set-power-for-device-power-states).

Callers of **PoSetPowerState** must be running at IRQL <= APC_LEVEL except when setting state to D0. When setting state to D0, callers can be running at IRQL <= DISPATCH_LEVEL.

## -see-also

[**IRP_MN_START_DEVICE**](/windows-hardware/drivers/kernel/irp-mn-start-device)

[**PoStartNextPowerIrp**](nf-ntifs-postartnextpowerirp.md)
