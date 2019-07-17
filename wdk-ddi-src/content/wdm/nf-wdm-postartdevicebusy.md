---
UID: NF:wdm.PoStartDeviceBusy
title: PoStartDeviceBusy function (wdm.h)
description: The PoStartDeviceBusy routine marks the start of a period of time in which the device is busy.
old-location: kernel\postartdevicebusy.htm
tech.root: kernel
ms.assetid: f3801fdf-c300-4863-afb9-49fad011dc4c
ms.date: 04/30/2018
ms.keywords: PoStartDeviceBusy, PoStartDeviceBusy routine [Kernel-Mode Driver Architecture], kernel.postartdevicebusy, portn_b129df72-9d6a-46b7-99db-ad2e96cfeafe.xml, wdm/PoStartDeviceBusy
ms.topic: function
f1_keywords:
 - "wdm/PoStartDeviceBusy"
req.header: wdm.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoStartDeviceBusy
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoStartDeviceBusy function


## -description


The <b>PoStartDeviceBusy</b> routine marks the start of a period of time in which the device is busy.


## -parameters




### -param IdlePointer [in, out]

A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoStartDeviceBusy</b>.


## -returns



None




## -remarks



The <b>PoStartDeviceBusy</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-poenddevicebusy">PoEndDeviceBusy</a> routines mark the start and end of a time period in which a device is busy. Each call to <b>PoStartDeviceBusy</b> must be followed by a corresponding call to <b>PoEndDeviceBusy</b>.

For each device, the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-manager">power manager</a> maintains a count of the number of outstanding <b>PoStartDeviceBusy</b> calls for which it has not yet received a corresponding <b>PoEndDeviceBusy</b> call. A <b>PoStartDeviceBusy</b> call increments the busy count by one. A <b>PoEndDeviceBusy</b> call decrements the busy count by one. A nonzero busy count disables the idle counter for the device. After the busy count reaches zero, the power manager resets the idle counter to the time-out period and enables the counter.

Rather than use the <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> routines to reset the idle counter, you can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-posetdevicebusyex">PoSetDeviceBusyEx</a> routine (or the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">PoSetDeviceBusy</a> macro). To disable the idle counter during an extended busy period, a driver can call the <b>PoRegisterDeviceForIdleDetection</b> routine to disable and enable idle notifications at the start and end of the busy period. However, <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> are typically more convenient to use for this purpose, and you should consider using these routines in new code that you write for Windows 7 and later versions of Windows.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-poenddevicebusy">PoEndDeviceBusy</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">PoSetDeviceBusy</a>
 

 

