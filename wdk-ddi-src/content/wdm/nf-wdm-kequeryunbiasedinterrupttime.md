---
UID: NF:wdm.KeQueryUnbiasedInterruptTime
title: KeQueryUnbiasedInterruptTime function
author: windows-driver-content
description: The KeQueryUnbiasedInterruptTime routine returns the current value of the system interrupt time count.
old-location: kernel\kequeryunbiasedinterrupttime.htm
old-project: kernel
ms.assetid: 2a041946-0335-466e-b2f9-b486031e777a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeQueryUnbiasedInterruptTime, KeQueryUnbiasedInterruptTime routine [Kernel-Mode Driver Architecture], k105_34119e3c-6e9a-4e27-9d0e-3d9eb579df46.xml, kernel.kequeryunbiasedinterrupttime, wdm/KeQueryUnbiasedInterruptTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryUnbiasedInterruptTime
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryUnbiasedInterruptTime function


## -description


The <b>KeQueryUnbiasedInterruptTime</b> routine returns the current value of the system <a href="http://go.microsoft.com/fwlink/p/?linkid=201082">interrupt time</a> count.


## -syntax


````
ULONGLONG KeQueryUnbiasedInterruptTime(void);
````


## -parameters






## -returns



<b>KeQueryUnbiasedInterruptTime</b> returns the current interrupt time count in 100-nanosecond units. The count begins at zero when the computer starts. Updates to this count are suspended when the computer enters a sleep state and are resumed when the computer awakens. 




## -remarks



Kernel-mode drivers can call this routine to measure relatively fine-grained durations.

This routine returns the system interrupt time, which is the amount of time since the operating system was last started. The interrupt-time count begins at zero when the operating system starts and is incremented at each clock interrupt by the length of a clock tick. For various reasons, such as hardware differences, the length of a system clock tick can vary between computers. Call the <a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a> routine to determine the size of a system clock tick.

<div class="alert"><b>Note</b>  The preceding remarks describe the behavior of <b>KeQueryUnbiasedInterruptTime</b> in free (or retail) builds of Windows. In checked (or debug) builds, this behavior is modified to help developers to identify bugs that might not occur until the operating system has been running for many days without being restarted. Specifically, the interrupt-time count and tick count in checked builds are advanced by approximately 49 days. For more information about checked and free builds, see <a href="https://msdn.microsoft.com/43aebfdb-2605-485c-a3a4-93e03b33aeca">Checked and Free Build Differences</a>.</div>
<div> </div>
The <b>KeQueryUnbiasedInterruptTime</b> and <a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a> routines are similar, but they differ in the way in which they account for periods in which the operating system suspends updates of the interrupt time count. For example, these updates are suspended while the computer is in a system sleep state. To compensate for periods in which updates of the count are suspended, <b>KeQueryInterruptTime</b> returns a biased count value that it calculates by adding a bias count to the raw interrupt time count. The bias count is the estimated sum of all of the updates to the interrupt time count that the operating system missed while counting was suspended. In contrast, <b>KeQueryUnbiasedInterruptTime</b> returns the raw, unbiased count.

Unlike the <a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a> routine, <b>KeQueryUnbiasedInterruptTime</b> returns a count value that is not affected by operations that set or reset the system time. In addition, the system time that is reported by <b>KeQuerySystemTime</b> is typically updated approximately every ten milliseconds. In contrast, the count that is returned by <b>KeQueryUnbiasedInterruptTime</b> is updated at least once per system clock tick.

In Windows 2000 and later versions of the Windows operating system, the <a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a> routine provides the finest grained running count that is available from the operating system.




## -see-also

<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>



<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>



<a href="..\wdm\nf-wdm-kequeryinterrupttimeprecise.md">KeQueryInterruptTimePrecise</a>



<a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a>



<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryUnbiasedInterruptTime routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

