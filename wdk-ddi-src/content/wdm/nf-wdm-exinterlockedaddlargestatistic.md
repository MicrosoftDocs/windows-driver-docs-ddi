---
UID: NF:wdm.ExInterlockedAddLargeStatistic
title: ExInterlockedAddLargeStatistic macro
description: The ExInterlockedAddLargeStatistic routine performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER variable.
old-location: kernel\exinterlockedaddlargestatistic.htm
tech.root: kernel
ms.assetid: f044a344-4768-499b-85b4-714062111b2c
ms.date: 04/30/2018
ms.keywords: ExInterlockedAddLargeStatistic, ExInterlockedAddLargeStatistic routine [Kernel-Mode Driver Architecture], k102_232887d0-d6f0-4664-bcff-221f371bfe6a.xml, kernel.exinterlockedaddlargestatistic, wdm/ExInterlockedAddLargeStatistic
ms.topic: macro
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExInterlockedAddLargeStatistic
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInterlockedAddLargeStatistic macro


## -description


The <b>ExInterlockedAddLargeStatistic</b> routine performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER variable.


## -parameters




### -param Addend [in]

A pointer to the LARGE_INTEGER variable that is incremented by the value of <i>Increment</i>.


### -param Increment [in]

Specifies a ULONG value that is added to the variable that <i>Addend</i> points to. 


## -remarks



Support routines that do interlocked operations must not cause a page fault. Neither their code nor any of the data they access can cause a page fault without bringing down the system. 

<b>ExInterlockedAddLargeStatistic</b> masks interrupts, and can be safely used to synchronize an ISR with other driver code.

<b>ExInterlockedAddLargeStatistic</b> runs at any IRQL. The storage for the <i>Addend</i> parameter must be resident at all IRQLs.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545335">ExInterlockedAddLargeInteger</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545343">ExInterlockedAddUlong</a>
 

 

