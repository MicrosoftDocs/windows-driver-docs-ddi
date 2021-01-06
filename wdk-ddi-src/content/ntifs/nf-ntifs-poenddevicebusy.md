---
UID: NF:ntifs.PoEndDeviceBusy
title: PoEndDeviceBusy function (ntifs.h)
description: The PoEndDeviceBusy routine marks the end of a period of time in which the device is busy.
old-location: kernel\poenddevicebusy.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PoEndDeviceBusy function"]
ms.keywords: PoEndDeviceBusy, PoEndDeviceBusy routine [Kernel-Mode Driver Architecture], kernel.poenddevicebusy, portn_edd72e85-e155-4a0c-9d6a-836ad448bb61.xml, wdm/PoEndDeviceBusy
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
 - PoEndDeviceBusy
 - ntifs/PoEndDeviceBusy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoEndDeviceBusy
---

# PoEndDeviceBusy function (ntifs.h)


## -description

The <b>PoEndDeviceBusy</b> routine marks the end of a period of time in which the device is busy.

## -parameters

### -param IdlePointer 

[in, out]
A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoEndDeviceBusy</b>.

## -remarks

The <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-postartdevicebusy">PoStartDeviceBusy</a> and <b>PoEndDeviceBusy</b> routines mark the start and end of a time period in which a device is busy. Each call to <b>PoStartDeviceBusy</b> must be followed by a corresponding call to <b>PoEndDeviceBusy</b>. For more information about how these routines work together, see <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-postartdevicebusy">PoStartDeviceBusy</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-postartdevicebusy">PoStartDeviceBusy</a>
