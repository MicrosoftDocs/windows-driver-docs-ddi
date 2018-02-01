---
UID: NF:wdm.ExAllocateTimer
title: ExAllocateTimer function
author: windows-driver-content
description: The ExAllocateTimer routine allocates and initializes a timer object.
old-location: kernel\exallocatetimer.htm
old-project: kernel
ms.assetid: 4FCFC48A-97BC-48E0-BBA7-F9E8B8A7588A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.exallocatetimer, ExAllocateTimer routine [Kernel-Mode Driver Architecture], ExAllocateTimer, wdm/ExAllocateTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ntoskrnl.lib
-	ntoskrnl.dll
apiname:
-	ExAllocateTimer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAllocateTimer function


## -description


The <b>ExAllocateTimer</b> routine allocates and initializes a timer object.


## -syntax


````
PEX_TIMER ExAllocateTimer(
  _In_opt_ PEXT_CALLBACK Callback,
  _In_opt_ PVOID         CallbackContext,
  _In_     ULONG         Attributes
);
````


## -parameters




### -param Callback [in, optional]

A pointer to a driver-implemented <a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a> callback routine. The operating system calls this routine when the timer expires. This parameter is optional and can be <b>NULL</b> if no callback routine is needed.


### -param CallbackContext [in, optional]

A context value for the callback routine pointed to by the <i>Callback</i> parameter. The operating system passes this value as a parameter to the <i>ExTimerCallback</i> callback routine, if one is specified. This parameter is typically a pointer to a caller-defined structure that contains context information used by the callback routine. This parameter is optional and can be set to <b>NULL</b> if no context information is needed.


### -param Attributes [in]

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


This routine returns a pointer to an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> structure, if the call is successful. This structure is the timer object that the routine has allocated and initialized. If the call fails, the routine returns <b>NULL</b>.



## -remarks


This routine returns a pointer to the new timer object. To use the timer, the calling driver supplies this pointer in subsequent calls to the <a href="..\wdm\nf-wdm-exsettimer.md">ExSetTimer</a>, <a href="..\wdm\nf-wdm-excanceltimer.md">ExCancelTimer</a>, and <a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a> routines. If the driver supplies a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a> callback routine as an input parameter to the <b>ExAllocateTimer</b> routine, the operating system passes this timer object as an input parameter to the <i>ExTimerCallback</i> routine.

A timer can be a notification timer or a synchronization timer. When a notification timer is signaled, all waiting threads have their wait satisfied. The state of this timer remains signaled until it is explicitly reset. When a synchronization timer expires, its state is set to signaled until a single waiting thread is released. Then, the timer is reset to the not-signaled state.

If the EX_TIMER_HIGH_RESOLUTION flag bit is set in <i>Attributes</i>, the operating system increases the resolution of the system clock, as necessary, so that the times at which the timer expires more precisely corresponds to the nominal expiration times specified in the <i>DueTime</i> and <i>Period</i> parameters to the <b>ExSetTimer</b> routine. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265247">High-Resolution Timers</a>.

If the EX_TIMER_NO_WAKE flag bit is set in <i>Attributes</i>, the timer avoids unnecessarily waking the processor from a low-power state. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265414">No-Wake Timers</a>.

<b>ExAllocateTimer</b> allocates the storage for the timer object. When this object is no longer needed, the caller is responsible for freeing this object by calling the <b>ExDeleteTimer</b> routine.

The <i>Callback</i> parameter is optional. A driver that does not supply an <i>ExTimerCallback</i> routine can instead initiate a wait operation on the timer object. A driver thread can call a routine such as <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a> or <a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a> to wait for the timer to expire. When the timer expires, the timer object is signaled.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265198">ExXxxTimer Routines and EX_TIMER Objects</a>.



## -see-also

<a href="..\wdm\nf-wdm-exsettimer.md">ExSetTimer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a>

<a href="..\wdm\nf-wdm-exdeletetimer.md">ExDeleteTimer</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a>

<a href="..\wdm\nf-wdm-excanceltimer.md">ExCancelTimer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocateTimer routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

