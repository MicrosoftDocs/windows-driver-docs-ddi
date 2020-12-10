---
UID: NF:wdm.ExAllocateTimer
title: ExAllocateTimer function (wdm.h)
description: The ExAllocateTimer routine allocates and initializes a timer object.
old-location: kernel\exallocatetimer.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExAllocateTimer function"]
ms.keywords: ExAllocateTimer, ExAllocateTimer routine [Kernel-Mode Driver Architecture], kernel.exallocatetimer, wdm/ExAllocateTimer
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExAllocateTimer
 - wdm/ExAllocateTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - ExAllocateTimer
---

# ExAllocateTimer function


## -description

The <b>ExAllocateTimer</b> routine allocates and initializes a timer object.

## -parameters

### -param Callback 

[in, optional]
A pointer to a driver-implemented <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ext_callback">ExTimerCallback</a> callback routine. The operating system calls this routine when the timer expires. This parameter is optional and can be <b>NULL</b> if no callback routine is needed.

### -param CallbackContext 

[in, optional]
A context value for the callback routine pointed to by the <i>Callback</i> parameter. The operating system passes this value as a parameter to the <i>ExTimerCallback</i> callback routine, if one is specified. This parameter is typically a pointer to a caller-defined structure that contains context information used by the callback routine. This parameter is optional and can be set to <b>NULL</b> if no context information is needed.

### -param Attributes 

[in]
The timer attributes. Set this parameter to zero or to the bitwise-OR of one or more of the following timer flag bits.

<table>
<tr>
<th>Timer flag bit</th>
<th>Description</th>
</tr>
<tr>
<td>EX_TIMER_HIGH_RESOLUTION</td>
<td>High-resolution timer. Make the timer more precise by using a higher-resolution clock to drive the timer.</td>
</tr>
<tr>
<td>EX_TIMER_NO_WAKE</td>
<td>No-wake timer. Make the timer delay waking the processor to expire until the timer's expiration time plus its delay tolerance is exceeded.</td>
</tr>
<tr>
<td>EX_TIMER_NOTIFICATION</td>
<td>Notification timer. Make the timer a notification timer instead of a synchronization timer. If this flag is not set, the timer is a synchronization timer.</td>
</tr>
</table>
 

The EX_TIMER_NOTIFICATION flag bit can be set regardless of what other flag bits are set.

The EX_TIMER_HIGH_RESOLUTION and EX_TIMER_NO_WAKE flag bits are mutually exclusive. If the caller sets both of these flag bits, the routine bug checks.

For more information about timer attributes, see Remarks.

## -returns

This routine returns a pointer to an <a href="/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> structure, if the call is successful. This structure is the timer object that the routine has allocated and initialized. If the call fails, the routine returns <b>NULL</b>.

## -remarks

This routine returns a pointer to the new timer object. To use the timer, the calling driver supplies this pointer in subsequent calls to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimer">ExSetTimer</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-excanceltimer">ExCancelTimer</a>, and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletetimer">ExDeleteTimer</a> routines. If the driver supplies a pointer to an <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ext_callback">ExTimerCallback</a> callback routine as an input parameter to the <b>ExAllocateTimer</b> routine, the operating system passes this timer object as an input parameter to the <i>ExTimerCallback</i> routine.

A timer can be a notification timer or a synchronization timer. When a notification timer is signaled, all waiting threads have their wait satisfied. The state of this timer remains signaled until it is explicitly reset. When a synchronization timer expires, its state is set to signaled until a single waiting thread is released. Then, the timer is reset to the not-signaled state.

If the EX_TIMER_HIGH_RESOLUTION flag bit is set in <i>Attributes</i>, the operating system increases the resolution of the system clock, as necessary, so that the times at which the timer expires more precisely corresponds to the nominal expiration times specified in the <i>DueTime</i> and <i>Period</i> parameters to the <b>ExSetTimer</b> routine. For more information, see <a href="/windows-hardware/drivers/kernel/high-resolution-timers">High-Resolution Timers</a>.

If the EX_TIMER_NO_WAKE flag bit is set in <i>Attributes</i>, the timer avoids unnecessarily waking the processor from a low-power state. For more information, see <a href="/windows-hardware/drivers/kernel/no-wake-timers">No-Wake Timers</a>.

<b>ExAllocateTimer</b> allocates the storage for the timer object. When this object is no longer needed, the caller is responsible for freeing this object by calling the <b>ExDeleteTimer</b> routine.

The <i>Callback</i> parameter is optional. A driver that does not supply an <i>ExTimerCallback</i> routine can instead initiate a wait operation on the timer object. A driver thread can call a routine such as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a> to wait for the timer to expire. When the timer expires, the timer object is signaled.

For more information, see <a href="/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">ExXxxTimer Routines and EX_TIMER Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-excanceltimer">ExCancelTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletetimer">ExDeleteTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimer">ExSetTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ext_callback">ExTimerCallback</a>
