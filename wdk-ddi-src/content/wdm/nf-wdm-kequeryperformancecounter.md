---
UID: NF:wdm.KeQueryPerformanceCounter
title: KeQueryPerformanceCounter function
author: windows-driver-content
description: The KeQueryPerformanceCounter routine retrieves the current value and frequency of the performance counter.Use KeQueryPerformanceCounter to acquire high resolution (&lt;1us) time stamps for time interval measurements.
old-location: kernel\kequeryperformancecounter.htm
old-project: kernel
ms.assetid: ee1dbd20-5502-4448-b39a-4629ddc73d01
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeQueryPerformanceCounter, KeQueryPerformanceCounter routine [Kernel-Mode Driver Architecture], k105_39f70923-56fe-42b1-bec3-fe23ae62904d.xml, kernel.kequeryperformancecounter, wdm/KeQueryPerformanceCounter
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
req.lib: Hal.lib
req.dll: Hal.dll
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hal.dll
api_name:
-	KeQueryPerformanceCounter
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryPerformanceCounter function


## -description


The <b>KeQueryPerformanceCounter</b> routine retrieves the current value and frequency of the performance counter.

Use <b>KeQueryPerformanceCounter</b> to acquire high resolution (&lt;1us) time stamps for time interval measurements.


## -parameters




### -param PerformanceFrequency [out, optional]

A pointer to a variable to which <b>KeQueryPerformanceCounter</b> writes the performance counter frequency, in ticks per second. This parameter is optional and can be NULL if the caller does not need the counter frequency value.


## -returns



<b>KeQueryPerformanceCounter</b> returns the performance counter value in units of ticks.




## -remarks



<b>KeQueryPerformanceCounter</b> returns a 64-bit integer that represents the current value of a high-resolution monotonically nondecreasing counter. 

To obtain the frequency of the performance counter, specify a non-<b>NULL</b> pointer value for the <i>PerformanceFrequency</i> parameter. The frequency of the performance counter is fixed at system boot and is consistent across all processors. Therefore, a driver can cache the frequency of the performance counter during initialization.  

For more info about this function and its usage, see <a href="https://msdn.microsoft.com/D66E0FC2-3AF2-489B-B4B5-78648905B77B">Acquiring high-resolution time stamps</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553025">KeQueryInterruptTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553068">KeQuerySystemTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553071">KeQueryTickCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553075">KeQueryTimeIncrement</a>



<a href="https://msdn.microsoft.com/08169390-940b-4110-813a-249d107cc953">QueryPerformanceCounter</a>



<a href="https://msdn.microsoft.com/f69367a4-0516-4033-81e3-90d4c5270a1e">QueryPerformanceFrequency</a>
 

 

