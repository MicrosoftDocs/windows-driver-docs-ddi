---
UID: NF:wdm.IoInitializeTimer
title: IoInitializeTimer function (wdm.h)
description: The IoInitializeTimer routine sets up a driver-supplied IoTimer routine associated with a given device object.
old-location: kernel\ioinitializetimer.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["IoInitializeTimer function"]
ms.keywords: IoInitializeTimer, IoInitializeTimer routine [Kernel-Mode Driver Architecture], k104_28bd2888-4ec7-4de8-b2ea-f006a8f39209.xml, kernel.ioinitializetimer, wdm/IoInitializeTimer
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoInitializeTimer
 - wdm/IoInitializeTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoInitializeTimer
---

# IoInitializeTimer function

## -description

The **IoInitializeTimer** routine sets up a driver-supplied [IoTimer](./nc-wdm-io_timer_routine.md) routine associated with a given device object.

## -parameters

### -param DeviceObject [in]

Pointer to a device object representing a device on which I/O operations can time out.

### -param TimerRoutine [in]

Pointer to the driver-supplied *IoTimer* routine.

### -param Context [in, optional]

Pointer to the driver-determined context with which its *IoTimer* routine will be called.

## -returns

**IoInitializeTimer** returns STATUS_SUCCESS if the *IoTimer* routine is set up.

## -remarks

**IoInitializeTimer** should be called only once per device object.

A driver's [IoTimer](./nc-wdm-io_timer_routine.md) routine is called once per second after the driver enables the timer by calling [IoStartTimer](../ntifs/nf-ntifs-iostarttimer.md). The driver can disable the timer by calling [IoStopTimer](../ntifs/nf-ntifs-iostoptimer.md) and can reenable it again with **IoStartTimer**.

The driver's *IoTimer* routine is called at IRQL = DISPATCH_LEVEL and therefore must not contain pageable code.

When the timer is running, the I/O manager calls the driver-supplied *IoTimer* routine once per second. Drivers whose time-out routines should be called at variable intervals or at intervals of finer granularity can set up a [CustomTimerDpc](/windows-hardware/drivers/kernel/using-a-customtimerdpc-routine) routine and use the **Ke*Xxx*Timer** routines.

## -see-also

[IoStartTimer](../ntifs/nf-ntifs-iostarttimer.md)

[IoStopTimer](../ntifs/nf-ntifs-iostoptimer.md)

[IoTimer](./nc-wdm-io_timer_routine.md)

[KeInitializeTimer](./nf-wdm-keinitializetimer.md)

[KeSetTimer](./nf-wdm-kesettimer.md)
