---
UID: NF:wdm.KeSetCoalescableTimer
title: KeSetCoalescableTimer function (wdm.h)
description: The KeSetCoalescableTimer routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times.
old-location: kernel\kesetcoalescabletimer.htm
tech.root: kernel
ms.assetid: e053c120-8c43-4714-acf1-0648958eabb8
ms.date: 04/30/2018
keywords: ["KeSetCoalescableTimer function"]
ms.keywords: KeSetCoalescableTimer, KeSetCoalescableTimer routine [Kernel-Mode Driver Architecture], k105_3e45ae54-682d-47f6-a577-28277cee4829.xml, kernel.kesetcoalescabletimer, wdm/KeSetCoalescableTimer
f1_keywords:
 - "wdm/KeSetCoalescableTimer"
 - "KeSetCoalescableTimer"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeSetCoalescableTimer
targetos: Windows
req.typenames: 
---

# KeSetCoalescableTimer function


## -description


The <b>KeSetCoalescableTimer</b> routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times. 


## -parameters




### -param Timer 
[in, out]
A pointer to a timer object. This parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KTIMER</a> structure, which is an opaque, system structure that represents the timer object. This object must have been previously initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimerex">KeInitializeTimerEx</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a> routine.


### -param DueTime 
[in]
Specifies an absolute or relative time at which the timer is to expire. If the value of the <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units, which are 100-nanosecond intervals. Absolute expiration times track any changes that are made to the system clock. Relative expiration times are not affected by system clock changes.


### -param Period 
[in]
Specifies the interval between periodic timer expirations in milliseconds. The value of this parameter must not exceed MAXLONG. This parameter is optional and can be set to zero to indicate that the timer is nonperiodic.


### -param TolerableDelay 
[in]
Specifies a tolerance, in milliseconds, for the timer period that <i>Period</i> specifies and for the initial time interval that <i>DueTime</i> specifies. For a periodic timer, the time interval between two successive timer expirations will be in the range from (<i>Period</i> - <i>TolerableDelay</i>) to (<i>Period</i> + <i>TolerableDelay</i>). The initial expiration time will be in the range from <i>DueTime</i> to (<i>DueTime</i> + <i>TolerableDelay</i>). The <i>TolerableDelay</i> value cannot be negative.


### -param Dpc 
[in, optional]
A pointer to a DPC object. This parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure, which is an opaque, system structure that represents the DPC object. This object must have been previously initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a> routine. This parameter is optional and can be specified as <b>NULL</b> if the caller does not require a DPC.


## -returns



<b>KeSetCoalescableTimer</b> returns <b>TRUE</b> if the timer object was already in the system timer queue. Otherwise, it returns <b>FALSE</b>. 




## -remarks



This routine does the following:

<ul>
<li>
Sets the timer to a nonsignaled state.

</li>
<li>
Associates the timer with the DPC, if a DPC is specified.

</li>
<li>
Cancels the timer if it is already active.

</li>
<li>
Makes the timer active and sets the due time and period of the timer to the specified values. The timer can expire immediately if the specified due time has already passed.

</li>
</ul>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a> routine is similar to <b>KeSetCoalescableTimer</b> but does not accept a <i>TolerableDelay</i> parameter. The <i>TolerableDelay</i> parameter of <b>KeSetCoalescableTimer</b> enables the caller to specify a tolerance for the timer period. A call to <b>KeSetCoalescableTimer</b> with <i>TolerableDelay</i> = 0 is the same as a call to <b>KeSetTimerEx</b>. In many instances, developers can easily modify existing drivers by replacing calls to <b>KeSetTimerEx</b> with calls to <b>KeSetCoalescableTimer</b>.

If two <b>KeSetCoalescableTimer</b> calls specify the same timer object, and the second call occurs before the <i>DueTime</i> that is specified for the first call expires, the second call implicitly cancels the timer from the first call. However, if a timer expiration from the first call has already enabled a DPC to run, the DPC might run after the timer is canceled. The second call replaces the pending expiration time from the first call with a new expiration time, and activates the timer again.

If the <i>Period</i> parameter is nonzero, the timer is periodic. For a periodic timer, the first timer expiration occurs at the time indicated by the <i>DueTime</i> parameter. Later expirations are separated by the interval that is specified by <i>Period</i>. If <i>Period</i> = 0, the timer is nonperiodic and expires at the time that is indicated by <i>DueTime</i>.

If the <i>Dpc</i> parameter is non-<b>NULL</b>, the routine creates an association between the specified DPC object and the timer object. After the timer expires, the timer service removes the timer object from the system timer queue and sets this object to a signaled state. If a DPC object is associated with the timer object, the timer service inserts the DPC object into the system DPC queue to run as soon as conditions allow.

Only one instance of a particular DPC object can be in the system DPC queue at a time. To avoid potential race conditions, avoid passing the same DPC object to both the <b>KeSetCoalescableTimer</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a> routines.

Avoid changing the importance or the target processor of a DPC that is associated with an active timer. Either cancel the timer or make sure that the timer has expired before you call a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesetimportancedpc">KeSetImportanceDpc</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettargetprocessordpcex">KeSetTargetProcessorDpcEx</a> to change the DPC settings. For example, if a driver updates the target processor of a DPC while a timer enables the DPC to run, the DPC might run on an arbitrary processor.

A periodic timer automatically restarts as soon as it expires. Therefore, in a multiprocessor system, the DPC for a periodic timer might be running on two or more processors at the same time.

Drivers must cancel any active timers in their <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routines. Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kecanceltimer">KeCancelTimer</a> routine to cancel a timer. If a DPC is associated with a timer that is periodic or that might recently have expired, a driver must wait (for example, by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keflushqueueddpcs">KeFlushQueuedDpcs</a> routine) to free the DPC and its associated data until all pending DPC executions on all processors finish. 

<b>KeSetCoalescableTimer</b> uses the <i>TolerableDelay</i> parameter to perform timer coalescing. That is, the routine adjusts the expiration times for the timer to coincide with the expiration times of other software timers. Timer coalescing helps increase the length of idle periods so that the operating system can reduce power consumption and improve energy efficiency.

To use timer coalescing effectively, a caller should specify a <i>TolerableDelay</i> value of at least 32 milliseconds. This value equals two default system clock intervals of 15.6 milliseconds. If you can, use a larger <i>TolerableDelay</i> value, such as 100 milliseconds.

Try to specify the <i>Period</i> and <i>TolerableDelay</i> values in multiples of 50 milliseconds. Typical <i>Period</i> values are 50, 100, 250, 500, and 1000 milliseconds. Typical <i>TolerableDelay</i> values are 50, 100, 150, and 250 milliseconds.

Typically, a timer with a large <i>Period</i> value can use a proportionally large <i>TolerableDelay</i> value. For example, a timer with <i>Period</i> = 500 milliseconds might use <i>TolerableDelay</i> = 50 milliseconds, but a timer with <i>Period</i> = 10 seconds might use <i>TolerableDelay</i> = 1 second.

Expiration times are measured relative to the system clock, and the accuracy with which the operating system can detect when a timer expires is limited by the granularity of the system clock. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/timer-accuracy">Timer Accuracy</a>.

For more information about timer objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/timer-objects-and-dpcs">Timer Objects and DPCs</a>. For more information about timer coalescing, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=116598">Windows Timer Coalescing</a> white paper on the WHDC website. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KTIMER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kecanceltimer">KeCancelTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keflushqueueddpcs">KeFlushQueuedDpcs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimerex">KeInitializeTimerEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesetimportancedpc">KeSetImportanceDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettargetprocessordpcex">KeSetTargetProcessorDpcEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a>
 

 

