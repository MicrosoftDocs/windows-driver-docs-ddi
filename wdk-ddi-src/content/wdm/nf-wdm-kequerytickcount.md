---
UID: NF:wdm.KeQueryTickCount
title: KeQueryTickCount macro (wdm.h)
description: The KeQueryTickCount routine maintains a count of the interval timer interrupts that have occurred since the system was booted.
old-location: kernel\kequerytickcount.htm
tech.root: kernel
ms.assetid: 7cd0ed27-a056-4ed9-8ff4-e917b31b0dd6
ms.date: 04/30/2018
keywords: ["KeQueryTickCount macro"]
ms.keywords: KeQueryTickCount, KeQueryTickCount routine [Kernel-Mode Driver Architecture], k105_a6a22896-6f3e-4e58-b443-4a06ff67b0ce.xml, kernel.kequerytickcount, wdm/KeQueryTickCount
f1_keywords:
 - "wdm/KeQueryTickCount"
 - "KeQueryTickCount"
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
- KeQueryTickCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryTickCount macro


## -description


The <b>KeQueryTickCount</b> routine maintains a count of the interval timer interrupts that have occurred since the system was booted. 


## -parameters




### -param CurrentCount [out]

Pointer to the LARGE_INTEGER tick count value on return from <b>KeQueryTickCount</b>.





## -remarks



The <i>TickCount</i> value increases by one at each interval timer interrupt while the system is running.

The preferred method of determining elapsed time is by using <i>TickCount</i> for relative timing and time stamps.

To determine the absolute elapsed time multiply the returned <i>TickCount</i> by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerytimeincrement">KeQueryTimeIncrement</a> return value using compiler support for 64-bit integer operations.

You should not make any assumptions about the length of a tick, because it might vary depending on hardware and other considerations. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryinterrupttime">KeQueryInterruptTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerytimeincrement">KeQueryTimeIncrement</a>
 

 

