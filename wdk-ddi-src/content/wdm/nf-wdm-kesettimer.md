---
UID: NF:wdm.KeSetTimer
title: KeSetTimer function
author: windows-driver-content
description: The KeSetTimer routine sets the absolute or relative interval at which a timer object is to be set to a signaled state and, optionally, supplies a CustomTimerDpc routine to be executed when that interval expires.
old-location: kernel\kesettimer.htm
old-project: kernel
ms.assetid: 81a205cd-a641-4f85-a217-7febf203b62d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeSetTimer, KeSetTimer routine [Kernel-Mode Driver Architecture], k105_9cd3cb17-0067-4340-8226-ee75392cfdd1.xml, kernel.kesettimer, wdm/KeSetTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeSetTimer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSetTimer function


## -description


The <b>KeSetTimer</b> routine sets the absolute or relative interval at which a timer object is to be set to a signaled state and, optionally, supplies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542983">CustomTimerDpc</a> routine to be executed when that interval expires. 


## -parameters




### -param Timer [in, out]

Pointer to a timer object that was initialized with <a href="https://msdn.microsoft.com/library/windows/hardware/ff552168">KeInitializeTimer</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552173">KeInitializeTimerEx</a>.


### -param DueTime [in]

Specifies the absolute or relative time at which the timer is to expire. If the value of the <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.


### -param Dpc [in, optional]

Pointer to a DPC object that was initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff552130">KeInitializeDpc</a>. This parameter is optional. 


## -returns



If the timer object was already in the system timer queue, <b>KeSetTimer</b> returns <b>TRUE</b>.




## -remarks



The <b>KeSetTimer</b> routine does the following:

<ul>
<li>
Computes the expiration time.

</li>
<li>
Sets the timer to a not-signaled state.

</li>
<li>
Inserts the timer object in the system timer queue.

</li>
</ul>
If the timer object was already in the timer queue, it is implicitly canceled before being set to the new expiration time. A call to <b>KeSetTimer</b> before the previously specified <i>DueTime</i> has expired cancels both the timer and the call to the <i>Dpc</i>, if any, associated with the previous call.

If the <i>Dpc</i> parameter is specified, a DPC object is associated with the timer object. When the timer expires, the timer object is removed from the system timer queue and its state is set to signaled. If a DPC object was associated with the timer when it was set, the DPC object is inserted in the system DPC queue to be executed as soon as conditions permit after the timer interval expires.

Expiration times are measured relative to the system clock, and the accuracy with which the operating system can detect when a timer expires is limited by the granularity of the system clock. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj602805">Timer Accuracy</a>.

Only one instantiation of a given DPC object can be queued at any given moment. To avoid potential race conditions, the DPC passed to <b>KeSetTimer</b> should <u>not</u> be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff552185">KeInsertQueueDpc</a>.

Drivers must cancel any active timers in their <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routines. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff551970">KeCancelTimer</a> to cancel any timers.

Callers of <b>KeSetTimer</b> can specify one expiration time for a timer. To set a recurring timer use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551970">KeCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552130">KeInitializeDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552168">KeInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552173">KeInitializeTimerEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553099">KeReadStateTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

