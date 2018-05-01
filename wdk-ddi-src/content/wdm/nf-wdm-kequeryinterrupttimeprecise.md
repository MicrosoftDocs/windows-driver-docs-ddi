---
UID: NF:wdm.KeQueryInterruptTimePrecise
title: KeQueryInterruptTimePrecise function
author: windows-driver-content
description: The KeQueryInterruptTimePrecise routine returns the current value of the system interrupt time count, with accuracy to within a microsecond.
old-location: kernel\kequeryinterrupttimeprecise.htm
old-project: kernel
ms.assetid: CCA03E61-6FEF-42BC-9407-A02432C50542
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: KeQueryInterruptTimePrecise, KeQueryInterruptTimePrecise routine [Kernel-Mode Driver Architecture], kernel.kequeryinterrupttimeprecise, wdm/KeQueryInterruptTimePrecise
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryInterruptTimePrecise
product: Windows
targetos: Windows
req.typenames: 
---

# KeQueryInterruptTimePrecise function


## -description


The <b>KeQueryInterruptTimePrecise</b> routine returns the current value of the system <a href="http://go.microsoft.com/fwlink/p/?linkid=201082">interrupt time</a> count, with accuracy to within a microsecond.


## -parameters




### -param QpcTimeStamp [out]

A pointer to a ULONG64 variable into which the routine writes the performance counter value used to interpolate the return value.


## -returns



The current interrupt-time count in 100-nanosecond units.




## -remarks



<b>KeQueryInterruptTimePrecise</b> returns the system's current interrupt time, which is the amount of time since the operating system was last started. <b>KeQueryInterruptTimePrecise</b> is similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553025">KeQueryInterruptTime</a> routine, but is more precise. 

The interrupt time reported by <a href="https://msdn.microsoft.com/library/windows/hardware/ff553025">KeQueryInterruptTime</a> is based on the latest tick of the system clock timer. The clock timer is the hardware timer that periodically generates interrupts for the system clock. The uniform period between clock timer interrupts is referred to as a system clock tick, and is typically in the range of 500 microseconds to 15.625 milliseconds, depending on the hardware platform. The interrupt time value retrieved by <b>KeQueryInterruptTime</b> is accurate within a system clock tick.

To provide an interrupt time value that is more precise than that of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553025">KeQueryInterruptTime</a>, <b>KeQueryInterruptTimePrecise</b> uses the system performance counter to measure the time elapsed since the last clock timer interrupt, and adds this time to the interrupt time associated with the latest clock time. The interrupt time reported by <b>KeQueryInterruptTimePrecise</b> is accurate to within a microsecond.

On some hardware platforms, a <b>KeQueryInterruptTimePrecise</b> call might be slower than a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553025">KeQueryInterruptTime</a> call. The reason is that <b>KeQueryInterruptTimePrecise</b> reads the performance counter, which can introduce an additional delay. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553053">KeQueryPerformanceCounter</a>.

Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553075">KeQueryTimeIncrement</a> routine to determine the size of a system clock tick.

<div class="alert"><b>Note</b>  The preceding remarks describe the behavior of <b>KeQueryInterruptTime</b> in free (or retail) builds of Windows. In checked (or debug) builds, this behavior is modified to help developers to identify bugs that might not occur until the operating system has been running for many days without being restarted. Specifically, the interrupt-time count and tick count in checked builds are advanced by approximately 49 days. For more information about checked and free builds, see <a href="https://msdn.microsoft.com/43aebfdb-2605-485c-a3a4-93e03b33aeca">Checked and Free Build Differences</a>.</div>
<div> </div>
Precise interrupt time can be used to measure very fine-grained durations while the system is running because operations that set or reset the system time have no effect on the system interrupt time count.

However, power-management state changes do affect the system interrupt time count. Maintenance of the interrupt time count is suspended during system sleep states. When a subsequent wake state transition occurs, the system adds a "bias" value to the interrupt time count to compensate for the estimated duration of such a sleep state. The interrupt time count that is returned by <b>KeQueryInterruptTimePrecise</b> includes this bias value. To obtain an unbiased interrupt time count, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553077">KeQueryUnbiasedInterruptTime</a>. A precise version of the unbiased interrupt time count is not currently available.




## -see-also




<a href="https://msdn.microsoft.com/D66E0FC2-3AF2-489B-B4B5-78648905B77B">Acquiring high-resolution time stamps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553025">KeQueryInterruptTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553075">KeQueryTimeIncrement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553077">KeQueryUnbiasedInterruptTime</a>
 

 

