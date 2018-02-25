---
UID: NF:wdm.KeQueryInterruptTimePrecise
title: KeQueryInterruptTimePrecise function
author: windows-driver-content
description: The KeQueryInterruptTimePrecise routine returns the current value of the system interrupt time count, with accuracy to within a microsecond.
old-location: kernel\kequeryinterrupttimeprecise.htm
old-project: kernel
ms.assetid: CCA03E61-6FEF-42BC-9407-A02432C50542
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , I, K, KeQueryInterruptTimePrecise, KeQueryInterruptTimePrecise routine [Kernel-Mode Driver Architecture], P, Q, T, c, e, i, kernel.kequeryinterrupttimeprecise, m, n, p, r, s, t, u, wdm/KeQueryInterruptTimePrecise, y"
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeQueryInterruptTimePrecise
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryInterruptTimePrecise function


## -description


The <b>KeQueryInterruptTimePrecise</b> routine returns the current value of the system <a href="http://go.microsoft.com/fwlink/p/?linkid=201082">interrupt time</a> count, with accuracy to within a microsecond.


## -syntax


````
ULONG64 KeQueryInterruptTimePrecise(
  _Out_ PULONG64 QpcTimeStamp
);
````


## -parameters




### -param QpcTimeStamp [out]

A pointer to a ULONG64 variable into which the routine writes the performance counter value used to interpolate the return value.


## -returns



The current interrupt-time count in 100-nanosecond units.




## -remarks



<b>KeQueryInterruptTimePrecise</b> returns the system's current interrupt time, which is the amount of time since the operating system was last started. <b>KeQueryInterruptTimePrecise</b> is similar to the <a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a> routine, but is more precise. 

The interrupt time reported by <a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a> is based on the latest tick of the system clock timer. The clock timer is the hardware timer that periodically generates interrupts for the system clock. The uniform period between clock timer interrupts is referred to as a system clock tick, and is typically in the range of 500 microseconds to 15.625 milliseconds, depending on the hardware platform. The interrupt time value retrieved by <b>KeQueryInterruptTime</b> is accurate within a system clock tick.

To provide an interrupt time value that is more precise than that of <a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a>, <b>KeQueryInterruptTimePrecise</b> uses the system performance counter to measure the time elapsed since the last clock timer interrupt, and adds this time to the interrupt time associated with the latest clock time. The interrupt time reported by <b>KeQueryInterruptTimePrecise</b> is accurate to within a microsecond.

On some hardware platforms, a <b>KeQueryInterruptTimePrecise</b> call might be slower than a <a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a> call. The reason is that <b>KeQueryInterruptTimePrecise</b> reads the performance counter, which can introduce an additional delay. For more information, see <a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>.

Call the <a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a> routine to determine the size of a system clock tick.

<div class="alert"><b>Note</b>  The preceding remarks describe the behavior of <b>KeQueryInterruptTime</b> in free (or retail) builds of Windows. In checked (or debug) builds, this behavior is modified to help developers to identify bugs that might not occur until the operating system has been running for many days without being restarted. Specifically, the interrupt-time count and tick count in checked builds are advanced by approximately 49 days. For more information about checked and free builds, see <a href="https://msdn.microsoft.com/43aebfdb-2605-485c-a3a4-93e03b33aeca">Checked and Free Build Differences</a>.</div>
<div> </div>
Precise interrupt time can be used to measure very fine-grained durations while the system is running because operations that set or reset the system time have no effect on the system interrupt time count.

However, power-management state changes do affect the system interrupt time count. Maintenance of the interrupt time count is suspended during system sleep states. When a subsequent wake state transition occurs, the system adds a "bias" value to the interrupt time count to compensate for the estimated duration of such a sleep state. The interrupt time count that is returned by <b>KeQueryInterruptTimePrecise</b> includes this bias value. To obtain an unbiased interrupt time count, use the <a href="..\wdm\nf-wdm-kequeryunbiasedinterrupttime.md">KeQueryUnbiasedInterruptTime</a>. A precise version of the unbiased interrupt time count is not currently available.




## -see-also

<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>



<a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a>



<a href="..\wdm\nf-wdm-kequeryunbiasedinterrupttime.md">KeQueryUnbiasedInterruptTime</a>



<a href="https://msdn.microsoft.com/D66E0FC2-3AF2-489B-B4B5-78648905B77B">Acquiring high-resolution time stamps</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryInterruptTimePrecise routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

