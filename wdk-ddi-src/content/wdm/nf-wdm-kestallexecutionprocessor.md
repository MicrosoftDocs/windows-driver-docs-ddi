---
UID: NF:wdm.KeStallExecutionProcessor
title: KeStallExecutionProcessor function
author: windows-driver-content
description: The KeStallExecutionProcessor routine stalls the caller on the current processor for a specified time interval.
old-location: kernel\kestallexecutionprocessor.htm
old-project: kernel
ms.assetid: 9f03af94-0a29-42f4-84f1-09d8d1c97dd6
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: KeStallExecutionProcessor, KeStallExecutionProcessor routine [Kernel-Mode Driver Architecture], k105_47405815-7368-4100-b39d-43f5a242f5c1.xml, kernel.kestallexecutionprocessor, wdm/KeStallExecutionProcessor
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
-	KeStallExecutionProcessor
product: Windows
targetos: Windows
req.typenames: 
---

# KeStallExecutionProcessor function


## -description


The <b>KeStallExecutionProcessor</b> routine stalls the caller on the current processor for a specified time interval.


## -parameters




### -param MicroSeconds [in]

Specifies the number of microseconds to stall.


## -returns



None




## -remarks



<b>KeStallExecutionProcessor</b> is a processor-dependent routine that busy-waits for at least the specified number of microseconds, but not significantly longer.

This routine is for use by device drivers and other software that must wait for an interval of less than a clock tick but more than for a few instructions. If you use this routine you must minimize the stall interval, typically to less than 50 microseconds. If a driver must wait for a longer interval, you should use a different <a href="https://msdn.microsoft.com/dfee2240-44df-43bc-8804-271203480664">synchronization technique</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551986">KeDelayExecutionThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

