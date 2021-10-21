---
UID: NF:ntifs.PoStartDeviceBusy
title: PoStartDeviceBusy function (ntifs.h)
description: The PoStartDeviceBusy routine in ntifs.h marks the start of a period of time in which the device is busy.
old-location: kernel\postartdevicebusy.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PoStartDeviceBusy function"]
ms.keywords: PoStartDeviceBusy, PoStartDeviceBusy routine [Kernel-Mode Driver Architecture], kernel.postartdevicebusy, portn_b129df72-9d6a-46b7-99db-ad2e96cfeafe.xml, wdm/PoStartDeviceBusy
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
 - PoStartDeviceBusy
 - ntifs/PoStartDeviceBusy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoStartDeviceBusy
---

# PoStartDeviceBusy function (ntifs.h)


## -description

The <b>PoStartDeviceBusy</b> routine marks the start of a period of time in which the device is busy.

## -parameters

### -param IdlePointer 

[in, out]
A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoStartDeviceBusy</b>.

## -remarks

The <b>PoStartDeviceBusy</b> and <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poenddevicebusy">PoEndDeviceBusy</a> routines mark the start and end of a time period in which a device is busy. Each call to <b>PoStartDeviceBusy</b> must be followed by a corresponding call to <b>PoEndDeviceBusy</b>.

For each device, the <a href="/windows-hardware/drivers/kernel/power-manager">power manager</a> maintains a count of the number of outstanding <b>PoStartDeviceBusy</b> calls for which it has not yet received a corresponding <b>PoEndDeviceBusy</b> call. A <b>PoStartDeviceBusy</b> call increments the busy count by one. A <b>PoEndDeviceBusy</b> call decrements the busy count by one. A nonzero busy count disables the idle counter for the device. After the busy count reaches zero, the power manager resets the idle counter to the time-out period and enables the counter.

Rather than use the <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> routines to reset the idle counter, you can call the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-posetdevicebusyex">PoSetDeviceBusyEx</a> routine (or the [PoSetDeviceBusy](../wdm/nf-wdm-posetdevicebusy.md) macro). To disable the idle counter during an extended busy period, a driver can call the <b>PoRegisterDeviceForIdleDetection</b> routine to disable and enable idle notifications at the start and end of the busy period. However, <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> are typically more convenient to use for this purpose, and you should consider using these routines in new code that you write for Windows 7 and later versions of Windows.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poenddevicebusy">PoEndDeviceBusy</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a>



[PoSetDeviceBusy](../wdm/nf-wdm-posetdevicebusy.md)