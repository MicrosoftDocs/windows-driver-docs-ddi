---
UID: NF:wdm.KeSetTimerEx
title: KeSetTimerEx function (wdm.h)
description: The KeSetTimerEx routine sets the absolute or relative interval at which a timer object is to be set to a signaled state, optionally supplies a CustomTimerDpc routine to be executed when that interval expires, and optionally supplies a recurring interval for the timer.
old-location: kernel\kesettimerex.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeSetTimerEx function"]
ms.keywords: KeSetTimerEx, KeSetTimerEx routine [Kernel-Mode Driver Architecture], k105_ca0b6adf-7903-485b-b29c-c406701c3032.xml, kernel.kesettimerex, wdm/KeSetTimerEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeSetTimerEx
 - wdm/KeSetTimerEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSetTimerEx
---

# KeSetTimerEx function

## -description

The **KeSetTimerEx** routine sets the absolute or relative interval at which a timer object is to be set to a signaled state, optionally supplies a [CustomTimerDpc](/windows-hardware/drivers/kernel/using-a-customtimerdpc-routine) routine to be executed when that interval expires, and optionally supplies a recurring interval for the timer.

## -parameters

### -param Timer [in, out]

Pointer to a timer object that was initialized with [KeInitializeTimer](./nf-wdm-keinitializetimer.md) or [KeInitializeTimerEx](./nf-wdm-keinitializetimerex.md).

### -param DueTime [in]

Specifies the absolute or relative time at which the timer is to expire. If the value of the *DueTime* parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

### -param Period [in]

Specifies an optional recurring interval for the timer in milliseconds. Must be a value that is greater than or equal to zero. If the value of this parameter is zero, the timer is a nonperiodic timer that does not automatically re-queue itself.

### -param Dpc [in, optional]

Pointer to a DPC object that was initialized by [KeInitializeDpc](./nf-wdm-keinitializedpc.md). This parameter is optional.

## -returns

If the timer object was already in the system timer queue, **KeSetTimerEx** returns **TRUE**.

## -remarks

The **KeSetTimerEx** routine does the following:

- Computes the expiration time.

- Sets the timer to a not-signaled state.

- Sets the recurring interval for the timer, if one was specified.

- Inserts the timer object in the system timer queue.

If the timer object was already in the timer queue, it is implicitly canceled before being set to the new expiration time. A call to **KeSetTimerEx** before the previously specified *DueTime* has expired cancels both the timer and the call to the *Dpc*, if any, associated with the previous call.

Expiration times are measured relative to the system clock, and the accuracy with which the operating system can detect when a timer expires is limited by the granularity of the system clock. For more information, see [Timer Accuracy](/windows-hardware/drivers/kernel/timer-accuracy).

If the *Dpc* parameter is specified, a DPC object is associated with the timer object. When the timer expires, the timer object is removed from the system timer queue and it is set to a signaled state. If a DPC object was associated with the timer when it was set, the DPC object is inserted in the system DPC queue to be executed as soon as conditions permit after the timer interval expires.

A DPC routine cannot deallocate a periodic timer. A DPC routine can deallocate a nonperiodic timer.

Note that a periodic timer is automatically restarted as soon as it expires. Thus, on a multiprocessor machine, the DPC for a periodic timer can be running on two processors simultaneously.

Only one instantiation of a given DPC object can be queued at any given moment. To avoid potential race conditions, the DPC passed to **KeSetTimerEx** should not be passed to [KeInsertQueueDpc](./nf-wdm-keinsertqueuedpc.md).

Drivers must cancel any active timers in their [Unload](./nc-wdm-driver_unload.md) routines. Use [KeCancelTimer](./nf-wdm-kecanceltimer.md) to cancel any timers.

For more information about timer objects, see [Timer Objects and DPCs](/windows-hardware/drivers/kernel/timer-objects-and-dpcs).

## -see-also

[KeCancelTimer](./nf-wdm-kecanceltimer.md)

[KeInitializeDpc](./nf-wdm-keinitializedpc.md)

[KeInitializeTimer](./nf-wdm-keinitializetimer.md)

[KeInitializeTimerEx](./nf-wdm-keinitializetimerex.md)

[KeReadStateTimer](./nf-wdm-kereadstatetimer.md)

[KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md)

[KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md)
