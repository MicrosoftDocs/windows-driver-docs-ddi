---
UID: NF:wdm.KeSetTimerEx
title: KeSetTimerEx function
author: windows-driver-content
description: The KeSetTimerEx routine sets the absolute or relative interval at which a timer object is to be set to a signaled state, optionally supplies a CustomTimerDpc routine to be executed when that interval expires, and optionally supplies a recurring interval for the timer.
old-location: kernel\kesettimerex.htm
old-project: kernel
ms.assetid: 9a2a092d-f9b5-42a2-9be4-bc934a9304fb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeSetTimerEx, KeSetTimerEx routine [Kernel-Mode Driver Architecture], k105_ca0b6adf-7903-485b-b29c-c406701c3032.xml, kernel.kesettimerex, wdm/KeSetTimerEx
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeSetTimerEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSetTimerEx function


## -description


The <b>KeSetTimerEx</b> routine sets the absolute or relative interval at which a timer object is to be set to a signaled state, optionally supplies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542983">CustomTimerDpc</a> routine to be executed when that interval expires, and optionally supplies a recurring interval for the timer.


## -syntax


````
BOOLEAN KeSetTimerEx(
  _Inout_  PKTIMER       Timer,
  _In_     LARGE_INTEGER DueTime,
  _In_     LONG          Period,
  _In_opt_ PKDPC         Dpc
);
````


## -parameters




### -param Timer [in, out]

Pointer to a timer object that was initialized with <a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a> or <a href="..\wdm\nf-wdm-keinitializetimerex.md">KeInitializeTimerEx</a>.


### -param DueTime [in]

Specifies the absolute or relative time at which the timer is to expire. If the value of the <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.


### -param Period [in]

Specifies an optional recurring interval for the timer in milliseconds. Must be a value that is greater than or equal to zero. If the value of this parameter is zero, the timer is a nonperiodic timer that does not automatically re-queue itself.


### -param Dpc [in, optional]

Pointer to a DPC object that was initialized by <a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>. This parameter is optional. 


## -returns


If the timer object was already in the system timer queue, <b>KeSetTimerEx</b> returns <b>TRUE</b>.



## -remarks


The <b>KeSetTimerEx</b> routine does the following:
<ul>
<li>
Computes the expiration time.

</li>
<li>
Sets the timer to a not-signaled state.

</li>
<li>
Sets the recurring interval for the timer, if one was specified.

</li>
<li>
Inserts the timer object in the system timer queue.

</li>
</ul>If the timer object was already in the timer queue, it is implicitly canceled before being set to the new expiration time. A call to <b>KeSetTimerEx</b> before the previously specified <i>DueTime</i> has expired cancels both the timer and the call to the <i>Dpc</i>, if any, associated with the previous call.

Expiration times are measured relative to the system clock, and the accuracy with which the operating system can detect when a timer expires is limited by the granularity of the system clock. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj602805">Timer Accuracy</a>.

If the <i>Dpc</i> parameter is specified, a DPC object is associated with the timer object. When the timer expires, the timer object is removed from the system timer queue and it is set to a signaled state. If a DPC object was associated with the timer when it was set, the DPC object is inserted in the system DPC queue to be executed as soon as conditions permit after the timer interval expires.

A DPC routine cannot deallocate a periodic timer. A DPC routine can deallocate a nonperiodic timer.

Note that a periodic timer is automatically restarted as soon as it expires. Thus, on a multiprocessor machine, the DPC for a periodic timer can be running on two processors simultaneously.

Only one instantiation of a given DPC object can be queued at any given moment. To avoid potential race conditions, the DPC passed to <b>KeSetTimerEx</b> should <u>not</u> be passed to <a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>.

Drivers must cancel any active timers in their <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routines. Use <a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a> to cancel any timers.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.



## -see-also

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>

<a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a>

<a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a>

<a href="..\wdm\nf-wdm-keinitializetimerex.md">KeInitializeTimerEx</a>

<a href="..\wdm\nf-wdm-kereadstatetimer.md">KeReadStateTimer</a>

<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetTimerEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

