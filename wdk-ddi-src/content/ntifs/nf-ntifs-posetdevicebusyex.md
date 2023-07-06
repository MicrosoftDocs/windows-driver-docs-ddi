---
UID: NF:ntifs.PoSetDeviceBusyEx
title: PoSetDeviceBusyEx function (ntifs.h)
description: Learn more about the PoSetDeviceBusyEx routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["PoSetDeviceBusyEx function"]
ms.keywords: PoSetDeviceBusyEx, PoSetDeviceBusyEx routine [Kernel-Mode Driver Architecture], kernel.posetdevicebusyex, portn_62143669-4381-4b4b-8d23-8b315d882c65.xml, wdm/PoSetDeviceBusyEx
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista with SP1
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - PoSetDeviceBusyEx
 - ntifs/PoSetDeviceBusyEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoSetDeviceBusyEx
---

# PoSetDeviceBusyEx function (ntifs.h)

## -description

The **PoSetDeviceBusyEx** routine notifies the [power manager](/windows-hardware/drivers/kernel/power-manager) that the device associated with the specified idle counter is busy.

## -parameters

### -param IdlePointer [in, out]

A pointer to an idle counter. This is a pointer value that was previously returned by the [**PoRegisterDeviceForIdleDetection**](nf-ntifs-poregisterdeviceforidledetection.md) routine. Because **PoRegisterDeviceForIdleDetection** might return a NULL pointer, the caller must verify that the pointer is non-NULL before it calls **PoSetDeviceBusyEx**.

## -remarks

This routine is a direct replacement for the [**PoSetDeviceBusy**](../wdm/nf-wdm-posetdevicebusy.md) macro. If you are writing new driver code for Windows Vista with Service Pack 1 (SP1) and later versions of Windows, call **PoSetDeviceBusyEx** instead of **PoSetDeviceBusy**.

A driver calls the **PoSetDeviceBusyEx** and **PoRegisterDeviceForIdleDetection** routines to enable system idle detection for its device. If a device that is registered for idle detection stays idle for the driver-specified time-out period, the power manager sends an [IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power) request to put the device in a requested sleep state.

**PoSetDeviceBusyEx** reports that the device is busy, so that the power manager can restart its idle countdown. If the device is in a sleep state, **PoSetDeviceBusyEx** does not change the state of the device. That is, it does not cause the system to send an **IRP_MN_SET_POWER** request to awaken the device.

**PoSetDeviceBusyEx** is designed for use with I/O operations that are relatively brief compared to the time-out period of the idle counter. For longer operations that might exceed this period, use the [**PoStartDeviceBusy**](nf-ntifs-postartdevicebusy.md) and [**PoEndDeviceBusy**](nf-ntifs-poenddevicebusy.md) routines instead.

A driver that makes multiple requests for brief I/O operations should call **PoSetDeviceBusyEx** for every I/O request that it makes.

## -see-also

[IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power)

[**PoEndDeviceBusy**](nf-ntifs-poenddevicebusy.md)

[**PoRegisterDeviceForIdleDetection**](nf-ntifs-poregisterdeviceforidledetection.md)

[**PoSetDeviceBusy**](../wdm/nf-wdm-posetdevicebusy.md)

[**PoStartDeviceBusy**](nf-ntifs-postartdevicebusy.md)
