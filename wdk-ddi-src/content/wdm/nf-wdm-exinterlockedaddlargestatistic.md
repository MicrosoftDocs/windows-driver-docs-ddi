---
UID: NF:wdm.ExInterlockedAddLargeStatistic
title: ExInterlockedAddLargeStatistic macro
author: windows-driver-content
description: The ExInterlockedAddLargeStatistic routine performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER variable.
old-location: kernel\exinterlockedaddlargestatistic.htm
old-project: kernel
ms.assetid: f044a344-4768-499b-85b4-714062111b2c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExInterlockedAddLargeStatistic routine [Kernel-Mode Driver Architecture], k102_232887d0-d6f0-4664-bcff-221f371bfe6a.xml, kernel.exinterlockedaddlargestatistic, ExInterlockedAddLargeStatistic, wdm/ExInterlockedAddLargeStatistic
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	ExInterlockedAddLargeStatistic
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInterlockedAddLargeStatistic macro


## -description


The <b>ExInterlockedAddLargeStatistic</b> routine performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER variable.


## -syntax


````
VOID ExInterlockedAddLargeStatistic(
  _In_ PLARGE_INTEGER Addend,
  _In_ ULONG          Increment
);
````


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

<a href="..\wdm\nf-wdm-exinterlockedaddulong.md">ExInterlockedAddUlong</a>

<a href="..\wdm\nf-wdm-exinterlockedaddlargeinteger.md">ExInterlockedAddLargeInteger</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedAddLargeStatistic routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

