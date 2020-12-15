---
UID: NF:wdm.KeQuerySystemTime~r1
title: KeQuerySystemTime function (wdm.h)
description: The KeQuerySystemTime routine obtains the current system time.
old-location: kernel\kequerysystemtime.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeQuerySystemTime function"]
ms.keywords: KeQuerySystemTime, KeQuerySystemTime routine [Kernel-Mode Driver Architecture], k105_0eaf1b30-c365-45ac-828c-fbcc7cd71ff3.xml, kernel.kequerysystemtime, wdm/KeQuerySystemTime
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - KeQuerySystemTime
 - wdm/KeQuerySystemTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeQuerySystemTime
---

# KeQuerySystemTime function


## -description

The <b>KeQuerySystemTime</b> routine obtains the current system time.

## -parameters

### -param CurrentCount

[out] Pointer to LARGE_INTEGER variable that receives the current time.

## -remarks

System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequerytickcount">KeQueryTickCount</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerytimeincrement">KeQueryTimeIncrement</a>
