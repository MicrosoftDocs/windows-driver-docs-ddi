---
UID: NF:wdm.KeQuerySystemTimePrecise
title: KeQuerySystemTimePrecise function (wdm.h)
description: The KeQuerySystemTimePrecise routine retrieves the current system time, and is more precise than the KeQuerySystemTime routine.
old-location: kernel\kequerysystemtimeprecise.htm
tech.root: kernel
ms.assetid: 4f5df2b5-e896-4519-aec9-5699155bb142
ms.date: 04/30/2018
keywords: ["KeQuerySystemTimePrecise function"]
ms.keywords: KeQuerySystemTimePrecise, KeQuerySystemTimePrecise routine [Kernel-Mode Driver Architecture], kernel.kequerysystemtimeprecise, wdm/KeQuerySystemTimePrecise
f1_keywords:
 - "wdm/KeQuerySystemTimePrecise"
 - "KeQuerySystemTimePrecise"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeQuerySystemTimePrecise
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQuerySystemTimePrecise function


## -description


The <b>KeQuerySystemTimePrecise</b> routine retrieves the current <a href="https://docs.microsoft.com/windows/desktop/SysInfo/system-time">system time</a>, and is more precise than the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime~r1">KeQuerySystemTime</a> routine.


## -parameters




### -param CurrentTime [out]

A pointer to a LARGE_INTEGER variable into which the routine writes the current system time.


## -remarks



System time is a count of 100-nanosecond intervals since January 1, 1601. This value is computed for the GMT time zone. To adjust this value for the local time zone, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a> routine.

<b>KeQuerySystemTimePrecise</b> is similar to the <b>KeQuerySystemTime</b> routine, but is more precise. The system time reported by <b>KeQuerySystemTime</b> is based on the latest tick of the system clock timer. The clock timer is the hardware timer that periodically generates interrupts for the system clock. The uniform period between clock timer interrupts is referred to as a system clock tick, and is typically in the range of 500 microseconds to 15.625 milliseconds, depending on the hardware platform. The system time value retrieved by <b>KeQuerySystemTime</b> is accurate within a system clock tick.

To provide a system time value that is more accurate than that of <b>KeQuerySystemTime</b>, <b>KeQuerySystemTimePrecise</b> uses the system performance counter to measure the time elapsed since the last clock timer interrupt, and adds this time to the system clock time that it calculates from the clock timer count. The system time reported by <b>KeQuerySystemTimePrecise</b> is accurate to within a microsecond.

On some hardware platforms, a <b>KeQuerySystemTimePrecise</b> call might be slower than a <b>KeQuerySystemTime</b> call. The reason is that <b>KeQuerySystemTimePrecise</b> reads the performance counter, which can introduce an additional delay. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>.


Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerytimeincrement">KeQueryTimeIncrement</a> routine to determine the duration of a system clock tick.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime~r1">KeQuerySystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequerytickcount">KeQueryTickCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerytimeincrement">KeQueryTimeIncrement</a>
 

 

