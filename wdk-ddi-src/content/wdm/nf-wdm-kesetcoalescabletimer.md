---
UID: NF:wdm.KeSetCoalescableTimer
title: KeSetCoalescableTimer function (wdm.h)
description: The KeSetCoalescableTimer routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times.
tech.root: kernel
ms.date: 03/13/2023
keywords: ["KeSetCoalescableTimer function"]
ms.keywords: KeSetCoalescableTimer, KeSetCoalescableTimer routine [Kernel-Mode Driver Architecture], k105_3e45ae54-682d-47f6-a577-28277cee4829.xml, kernel.kesetcoalescabletimer, wdm/KeSetCoalescableTimer
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeSetCoalescableTimer
 - wdm/KeSetCoalescableTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSetCoalescableTimer
---

## -description

The **KeSetCoalescableTimer** routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times.

## -parameters

### -param Timer [in, out]

A pointer to a timer object. This parameter points to a [KTIMER](/windows-hardware/drivers/kernel/eprocess) structure, which is an opaque, system structure that represents the timer object. This object must have been previously initialized by the [KeInitializeTimerEx](./nf-wdm-keinitializetimerex.md) or [KeInitializeTimer](./nf-wdm-keinitializetimer.md) routine.

### -param DueTime [in]

Specifies an absolute or relative time at which the timer is to expire. If the value of the *DueTime* parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units, which are 100-nanosecond intervals. Absolute expiration times track any changes that are made to the system clock. Relative expiration times are not affected by system clock changes.

### -param Period [in]

Specifies the interval between periodic timer expirations in milliseconds. The value of this parameter must not exceed MAXLONG. This parameter is optional and can be set to zero to indicate that the timer is nonperiodic.

### -param TolerableDelay [in]

Specifies a tolerance, in milliseconds, for the timer period that *Period* specifies and for the initial time interval that *DueTime* specifies. For a periodic timer, the time interval between two successive timer expirations will be in the range from (*Period* - *TolerableDelay*) to (*Period* + *TolerableDelay*). The initial expiration time will be in the range from *DueTime* to (*DueTime* + *TolerableDelay*). The *TolerableDelay* value cannot be negative.

### -param Dpc [in, optional]

A pointer to a DPC object. This parameter points to a [KDPC](/windows-hardware/drivers/kernel/eprocess) structure, which is an opaque, system structure that represents the DPC object. This object must have been previously initialized by the [KeInitializeDpc](./nf-wdm-keinitializedpc.md) routine. This parameter is optional and can be specified as **NULL** if the caller does not require a DPC.

## -returns

**KeSetCoalescableTimer** returns **TRUE** if the timer object was already in the system timer queue. Otherwise, it returns **FALSE**.

## -remarks

This routine does the following:

- Sets the timer to a non-signaled state.

- Associates the timer with the DPC, if a DPC is specified.

- Cancels the timer if it is already active.

- Makes the timer active and sets the due time and period of the timer to the specified values. The timer can expire immediately if the specified due time has already passed.

The [KeSetTimerEx](./nf-wdm-kesettimerex.md) routine is similar to **KeSetCoalescableTimer** but does not accept a *TolerableDelay* parameter. The *TolerableDelay* parameter of **KeSetCoalescableTimer** enables the caller to specify a tolerance for the timer period. A call to **KeSetCoalescableTimer** with *TolerableDelay* = 0 is the same as a call to **KeSetTimerEx**. In many instances, developers can easily modify existing drivers by replacing calls to **KeSetTimerEx** with calls to **KeSetCoalescableTimer**.

If two **KeSetCoalescableTimer** calls specify the same timer object, and the second call occurs before the *DueTime* that is specified for the first call expires, the second call implicitly cancels the timer from the first call. However, if a timer expiration from the first call has already enabled a DPC to run, the DPC might run after the timer is canceled. The second call replaces the pending expiration time from the first call with a new expiration time, and activates the timer again.

If the *Period* parameter is nonzero, the timer is periodic. For a periodic timer, the first timer expiration occurs at the time indicated by the *DueTime* parameter. Later expirations are separated by the interval that is specified by *Period*. If *Period* = 0, the timer is nonperiodic and expires at the time that is indicated by *DueTime*.

If the *Dpc* parameter is non-**NULL**, the routine creates an association between the specified DPC object and the timer object. After the timer expires, the timer service removes the timer object from the system timer queue and sets this object to a signaled state. If a DPC object is associated with the timer object, the timer service inserts the DPC object into the system DPC queue to run as soon as conditions allow.

Only one instance of a particular DPC object can be in the system DPC queue at a time. To avoid potential race conditions, avoid passing the same DPC object to both the **KeSetCoalescableTimer** and [KeInsertQueueDpc](./nf-wdm-keinsertqueuedpc.md) routines.

Avoid changing the importance or the target processor of a DPC that is associated with an active timer. Either cancel the timer or make sure that the timer has expired before you call a routine such as [KeSetImportanceDpc](../ntddk/nf-ntddk-kesetimportancedpc.md) or [KeSetTargetProcessorDpcEx](./nf-wdm-kesettargetprocessordpcex.md) to change the DPC settings. For example, if a driver updates the target processor of a DPC while a timer enables the DPC to run, the DPC might run on an arbitrary processor.

A periodic timer automatically restarts as soon as it expires. Therefore, in a multiprocessor system, the DPC for a periodic timer might be running on two or more processors at the same time.

Drivers must cancel any active timers in their [Unload](./nc-wdm-driver_unload.md) routines. Call the [KeCancelTimer](./nf-wdm-kecanceltimer.md) routine to cancel a timer. If a DPC is associated with a timer that is periodic or that might recently have expired, a driver must wait (for example, by calling the [KeFlushQueuedDpcs](./nf-wdm-keflushqueueddpcs.md) routine) to free the DPC and its associated data until all pending DPC executions on all processors finish.

**KeSetCoalescableTimer** uses the *TolerableDelay* parameter to perform timer coalescing. That is, the routine adjusts the expiration times for the timer to coincide with the expiration times of other software timers. Timer coalescing helps increase the length of idle periods so that the operating system can reduce power consumption and improve energy efficiency.

To use timer coalescing effectively, a caller should specify a *TolerableDelay* value of at least 32 milliseconds. This value equals two default system clock intervals of 15.6 milliseconds. If you can, use a larger *TolerableDelay* value, such as 100 milliseconds.

Try to specify the *Period* and *TolerableDelay* values in multiples of 50 milliseconds. Typical *Period* values are 50, 100, 250, 500, and 1000 milliseconds. Typical *TolerableDelay* values are 50, 100, 150, and 250 milliseconds.

Typically, a timer with a large *Period* value can use a proportionally large *TolerableDelay* value. For example, a timer with *Period* = 500 milliseconds might use *TolerableDelay* = 50 milliseconds, but a timer with *Period* = 10 seconds might use *TolerableDelay* = 1 second.

Expiration times are measured relative to the system clock, and the accuracy with which the operating system can detect when a timer expires is limited by the granularity of the system clock. For more information, see [Timer Accuracy](/windows-hardware/drivers/kernel/timer-accuracy).

For more information about timer objects, see [Timer Objects and DPCs](/windows-hardware/drivers/kernel/timer-objects-and-dpcs). For more information about timer coalescing, see the [Windows Timer Coalescing](https://download.microsoft.com/download/9/C/5/9C5B2167-8017-4BAE-9FDE-D599BAC8184A/TimerCoal.docx) white paper on the WHDC website.

## -see-also

[KDPC](/windows-hardware/drivers/kernel/eprocess)

[KTIMER](/windows-hardware/drivers/kernel/eprocess)

[KeCancelTimer](./nf-wdm-kecanceltimer.md)

[KeFlushQueuedDpcs](./nf-wdm-keflushqueueddpcs.md)

[KeInitializeDpc](./nf-wdm-keinitializedpc.md)

[KeInitializeTimer](./nf-wdm-keinitializetimer.md)

[KeInitializeTimerEx](./nf-wdm-keinitializetimerex.md)

[KeInsertQueueDpc](./nf-wdm-keinsertqueuedpc.md)

[KeSetImportanceDpc](../ntddk/nf-ntddk-kesetimportancedpc.md)

[KeSetTargetProcessorDpcEx](./nf-wdm-kesettargetprocessordpcex.md)

[KeSetTimerEx](./nf-wdm-kesettimerex.md)

[Unload](./nc-wdm-driver_unload.md)