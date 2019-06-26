---
UID: NF:wdm.KeQueryTimeIncrement
title: KeQueryTimeIncrement function (wdm.h)
description: The KeQueryTimeIncrement routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.
old-location: kernel\kequerytimeincrement.htm
tech.root: kernel
ms.assetid: f8291e2b-a7a1-4a19-9137-fcd93e62bbaf
ms.date: 04/30/2018
ms.keywords: KeQueryTimeIncrement, KeQueryTimeIncrement routine [Kernel-Mode Driver Architecture], k105_dc7a4658-7d4b-4b60-a8c8-693c36d68b27.xml, kernel.kequerytimeincrement, wdm/KeQueryTimeIncrement
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeQueryTimeIncrement
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryTimeIncrement function


## -description


The <b>KeQueryTimeIncrement</b> routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.


## -parameters






## -returns



<b>KeQueryTimeIncrement</b> returns a ULONG value indicating the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.




## -remarks



At startup time, the operating system determines the time increment to use for the system time. This time increment remains constant until the computer restarts. During this time, calls to <b>KeQueryTimeIncrement</b> always return the same time increment value. The time increment does not change while the computer is running, and it does not change as the result of a suspend-resume cycle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-kequerytickcount">KeQueryTickCount</a>
 

 

