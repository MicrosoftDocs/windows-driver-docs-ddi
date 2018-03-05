---
UID: NF:wdm.KeQuerySystemTimePrecise
title: KeQuerySystemTimePrecise function
author: windows-driver-content
description: The KeQuerySystemTimePrecise routine retrieves the current system time, and is more precise than the KeQuerySystemTime routine.
old-location: kernel\kequerysystemtimeprecise.htm
old-project: kernel
ms.assetid: 4f5df2b5-e896-4519-aec9-5699155bb142
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeQuerySystemTimePrecise, KeQuerySystemTimePrecise routine [Kernel-Mode Driver Architecture], kernel.kequerysystemtimeprecise, wdm/KeQuerySystemTimePrecise
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
-	KeQuerySystemTimePrecise
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQuerySystemTimePrecise function


## -description


The <b>KeQuerySystemTimePrecise</b> routine retrieves the current <a href="https://msdn.microsoft.com/1a1e251e-2375-4134-bbd8-1e4670b9f9d2">system time</a>, and is more precise than the <a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a> routine.


## -syntax


````
VOID KeQuerySystemTimePrecise(
  _Out_ PLARGE_INTEGER CurrentTime
);
````


## -parameters




### -param CurrentTime [out]

A pointer to a LARGE_INTEGER variable into which the routine writes the current system time.


## -returns



None




## -remarks



System time is a count of 100-nanosecond intervals since January 1, 1601. This value is computed for the GMT time zone. To adjust this value for the local time zone, call the <a href="..\wdm\nf-wdm-exsystemtimetolocaltime.md">ExSystemTimeToLocalTime</a> routine.

<b>KeQuerySystemTimePrecise</b> is similar to the <b>KeQuerySystemTime</b> routine, but is more precise. The system time reported by <b>KeQuerySystemTime</b> is based on the latest tick of the system clock timer. The clock timer is the hardware timer that periodically generates interrupts for the system clock. The uniform period between clock timer interrupts is referred to as a system clock tick, and is typically in the range of 500 microseconds to 15.625 milliseconds, depending on the hardware platform. The system time value retrieved by <b>KeQuerySystemTime</b> is accurate within a system clock tick.

To provide a system time value that is more accurate than that of <b>KeQuerySystemTime</b>, <b>KeQuerySystemTimePrecise</b> uses the system performance counter to measure the time elapsed since the last clock timer interrupt, and adds this time to the system clock time that it calculates from the clock timer count. The system time reported by <b>KeQuerySystemTimePrecise</b> is accurate to within a microsecond.

On some hardware platforms, a <b>KeQuerySystemTimePrecise</b> call might be slower than a <b>KeQuerySystemTime</b> call. The reason is that <b>KeQuerySystemTimePrecise</b> reads the performance counter, which can introduce an additional delay. For more information, see <a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>.


Call the <a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a> routine to determine the duration of a system clock tick.




## -see-also

<a href="..\ntddk\nf-ntddk-kequerytickcount.md">KeQueryTickCount</a>



<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>



<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>



<a href="..\wdm\nf-wdm-exsystemtimetolocaltime.md">ExSystemTimeToLocalTime</a>



<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQuerySystemTimePrecise routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

