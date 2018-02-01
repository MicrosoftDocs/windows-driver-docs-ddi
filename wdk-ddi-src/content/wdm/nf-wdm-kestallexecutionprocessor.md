---
UID: NF:wdm.KeStallExecutionProcessor
title: KeStallExecutionProcessor function
author: windows-driver-content
description: The KeStallExecutionProcessor routine stalls the caller on the current processor for a specified time interval.
old-location: kernel\kestallexecutionprocessor.htm
old-project: kernel
ms.assetid: 9f03af94-0a29-42f4-84f1-09d8d1c97dd6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_47405815-7368-4100-b39d-43f5a242f5c1.xml, wdm/KeStallExecutionProcessor, KeStallExecutionProcessor, KeStallExecutionProcessor routine [Kernel-Mode Driver Architecture], kernel.kestallexecutionprocessor
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hal.dll
apiname:
-	KeStallExecutionProcessor
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeStallExecutionProcessor function


## -description


The <b>KeStallExecutionProcessor</b> routine stalls the caller on the current processor for a specified time interval.


## -syntax


````
 VOID KeStallExecutionProcessor(
  _In_ ULONG MicroSeconds
);
````


## -parameters




### -param MicroSeconds [in]

Specifies the number of microseconds to stall.


## -returns


None



## -remarks


<b>KeStallExecutionProcessor</b> is a processor-dependent routine that busy-waits for at least the specified number of microseconds, but not significantly longer.

This routine is for use by device drivers and other software that must wait for an interval of less than a clock tick but more than for a few instructions. If you use this routine you must minimize the stall interval, typically to less than 50 microseconds. If a driver must wait for a longer interval, you should use a different <a href="https://msdn.microsoft.com/dfee2240-44df-43bc-8804-271203480664">synchronization technique</a>.



## -see-also

<a href="..\wdm\nf-wdm-kedelayexecutionthread.md">KeDelayExecutionThread</a>

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeStallExecutionProcessor routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

