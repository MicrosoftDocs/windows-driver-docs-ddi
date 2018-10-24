---
UID: NF:wdm.ExSetTimer
title: ExSetTimer function
author: windows-driver-content
description: The ExSetTimer routine starts a timer operation and sets the timer to expire at the specified due time.
old-location: kernel\exsettimer.htm
tech.root: kernel
ms.assetid: 0320AB36-CA88-40E7-859E-B940401474DD
ms.date: 04/30/2018
ms.keywords: ExSetTimer, ExSetTimer routine [Kernel-Mode Driver Architecture], kernel.exsettimer, wdm/ExSetTimer
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	ExSetTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExSetTimer function


## -description


The <b>ExSetTimer</b> routine starts a timer operation and sets the timer to expire at the specified due time.


## -parameters




### -param Timer [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> structure. This structure is a timer object that was previously allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine.


### -param DueTime [in]

The absolute or relative time at which the timer is to expire. If the value of the <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes. An absolute time is expressed as the amount of time passed, in system time units, since the start of the year 1601.

The <i>DueTime</i> parameter for a <a href="https://msdn.microsoft.com/B8F2B28C-A02B-4015-B392-3D30BC0229B8">high-resolution timer</a> must be a relative time (negative value), or the routine bug checks.


### -param Period [in]

An optional period for the timer in system time units (100-nanosecond intervals). Must be less than or equal to MAXLONG. For a timer that is one-shot instead of periodic, set <i>Period</i> to zero.


### -param Parameters [in, optional]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265196">EXT_SET_PARAMETERS</a> structure. The calling driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265183">ExInitializeSetTimerParameters</a> routine to initialize this structure.


## -returns



This routine returns <b>TRUE</b> if it cancels a timer that was pending at the time that the routine was called. Otherwise, the routine returns <b>FALSE</b>. For more information, see Remarks.




## -remarks



Your driver can call this routine to set a timer to expire at a future time. The driver can then wait for the timer to expire. Or, the driver can implement a callback routine that is called when the timer expires.

After a driver calls <b>ExSetTimer</b>, the driver can call a routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a> or or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a> to wait for the timer to expire. When the timer expires, the operating system signals the timer object.

As an option, the driver can implement an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a> callback routine, and supply a pointer to this routine as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine. When the timer expires, the operating system calls the <i>ExTimerCallback</i> routine.

An <b>ExSetTimer</b> call implicitly cancels any previously started set-timer operation on the timer object specified by <i>Timer</i>. If your driver previously called <b>ExSetTimer</b> to set a timer that uses <i>Timer</i>, and this timer has not yet expired when <b>ExSetTimer</b> is called a second time, the second call cancels the timer from the first call and then starts the new timer. In this case, the second call returns <b>TRUE</b>. However, if the timer started by the first call expires before the second call can cancel this timer, the second call starts the new timer and returns <b>FALSE</b>.

If the <i>Period</i> parameter is nonzero, the timer is periodic. For a periodic timer, the <i>DueTime</i> parameter specifies the time of the initial timer expiration, and <i>Period</i> specifies the interval between subsequent expirations.

The hardware timer used for the system clock signals interrupt requests at uniform intervals, but the handling of these interrupts might be delayed by interrupt processing for other devices. Thus, for a periodic timer, the delay from a periodic expiration time to the time at which the timer object is signaled or the <i>ExTimerCallback</i> routine runs might vary from one period to the next. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj602805">Timer Accuracy</a>.

A periodic timer can expire no more than once per system clock tick. Setting the period of a timer to a value smaller than the interval between system clock ticks does not cause the timer to expire more than once per system clock tick, but might cause the intervals between successive expirations to vary if the system clock rate changes. For example, the operating system might temporarily increase the system clock rate to meet the timing requirements of a high-resolution timer. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265247">High-Resolution Timers</a>.

For a periodic timer that is not a high-resolution timer, a driver can achieve relatively uniform periodic expirations by setting <i>Period</i> to an integer multiple of the default interval between system clock ticks.

To avoid excessive power consumption, a driver should not set the period of a long-running high-resolution timer to a value less than the default interval between system clock ticks. Otherwise, the system clock timer will continuously generate interrupts at the maximum allowed system clock rate.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265198">ExXxxTimer Routines and EX_TIMER Objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265196">EXT_SET_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265183">ExInitializeSetTimerParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

