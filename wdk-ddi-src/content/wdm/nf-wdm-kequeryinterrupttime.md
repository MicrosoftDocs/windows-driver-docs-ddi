---
UID: NF:wdm.KeQueryInterruptTime
title: KeQueryInterruptTime function
author: windows-driver-content
description: The KeQueryInterruptTime routine returns the current value of the system interrupt time count, with accuracy to within system clock tick.
old-location: kernel\kequeryinterrupttime.htm
old-project: kernel
ms.assetid: 88c87b11-b34f-43b3-b08e-940abaa23a27
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeQueryInterruptTime, KeQueryInterruptTime routine [Kernel-Mode Driver Architecture], k105_a87c40d1-b9be-42f1-ada4-6e0fb3d33220.xml, kernel.kequeryinterrupttime, wdm/KeQueryInterruptTime
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
-	KeQueryInterruptTime
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryInterruptTime function


## -description


The <b>KeQueryInterruptTime</b> routine returns the current value of the system <a href="http://go.microsoft.com/fwlink/p/?linkid=201082">interrupt time</a> count, with accuracy to within system clock tick.


## -parameters






## -returns



<b>KeQueryInterruptTime</b> returns the current interrupt-time count in 100-nanosecond units. The update to this return value generally occurs at least once per system clock tick.




## -remarks



This routine returns the system interrupt time, which is the amount of time since the operating system was last started. The interrupt-time count begins at zero when the operating system starts and is incremented at each clock interrupt by the length of a clock tick. For various reasons, such as hardware differences, the length of a system clock tick can vary between computers. Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553075">KeQueryTimeIncrement</a> routine to determine the size of a system clock tick.

<div class="alert"><b>Note</b>  The preceding remarks describe the behavior of <b>KeQueryInterruptTime</b> in free (or retail) builds of Windows. In checked (or debug) builds, this behavior is modified to help developers to identify bugs that might not occur until the operating system has been running for many days without being restarted. Specifically, the interrupt-time count and tick count in checked builds are advanced by approximately 49 days. For more information about checked and free builds, see <a href="https://msdn.microsoft.com/43aebfdb-2605-485c-a3a4-93e03b33aeca">Checked and Free Build Differences</a>.</div>
<div> </div>
<b>KeQueryInterruptTime</b> can be used for performance tuning. This routine returns a finer grained measurement than the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553071">KeQueryTickCount</a> routine. A call to <b>KeQueryInterruptTime</b> has considerably less overhead than a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553053">KeQueryPerformanceCounter</a> routine, as well.

Consequently, interrupt time can be used to measure very fine-grained durations while the system is running because operations that set or reset the system time have no effect on the system interrupt time count.

However, power-management state changes do affect the system interrupt time count. Maintenance of the interrupt time count is suspended during system sleep states. When a subsequent wake state transition occurs, the system adds a "bias" value to the interrupt time count to compensate for the estimated duration of such a sleep state. The interrupt time count that is returned by <b>KeQueryInterruptTime</b> includes this bias value. To obtain an unbiased interrupt time count, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553077">KeQueryUnbiasedInterruptTime</a> routine instead of <b>KeQueryInterruptTime</b>.




## -see-also




<a href="https://msdn.microsoft.com/D66E0FC2-3AF2-489B-B4B5-78648905B77B">Acquiring high-resolution time stamps</a>



<b>KeQueryInterruptTimePrecise</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553053">KeQueryPerformanceCounter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553071">KeQueryTickCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553075">KeQueryTimeIncrement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553077">KeQueryUnbiasedInterruptTime</a>
 

 

