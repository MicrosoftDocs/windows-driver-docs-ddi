---
UID: NF:ntifs.PoEndDeviceBusy
title: PoEndDeviceBusy function (ntifs.h)
description: Learn more about the PoEndDeviceBusy routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["PoEndDeviceBusy function"]
ms.keywords: PoEndDeviceBusy, PoEndDeviceBusy routine [Kernel-Mode Driver Architecture], kernel.poenddevicebusy, portn_edd72e85-e155-4a0c-9d6a-836ad448bb61.xml, wdm/PoEndDeviceBusy
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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

The **PoEndDeviceBusy** routine marks the end of a period of time in which the device is busy.

## -parameters

### -param IdlePointer [in, out]

A pointer to an idle counter. This is a pointer value that was previously returned by the [**PoRegisterDeviceForIdleDetection**](nf-ntifs-poregisterdeviceforidledetection.md) routine. Because **PoRegisterDeviceForIdleDetection** might return a NULL pointer, the caller must verify that the pointer is non-NULL before it calls **PoEndDeviceBusy**.

## -remarks

The [**PoStartDeviceBusy**](nf-ntifs-postartdevicebusy.md) and **PoEndDeviceBusy** routines mark the start and end of a time period in which a device is busy. Each call to **PoStartDeviceBusy** must be followed by a corresponding call to **PoEndDeviceBusy**. For more information about how these routines work together, see [**PoStartDeviceBusy**](nf-ntifs-postartdevicebusy.md).

## -see-also

[**PoRegisterDeviceForIdleDetection**](nf-ntifs-poregisterdeviceforidledetection.md)

[**PoStartDeviceBusy**](nf-ntifs-postartdevicebusy.md)
