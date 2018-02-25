---
UID: NF:wdm.RtlSetAllBits
title: RtlSetAllBits function
author: windows-driver-content
description: The RtlSetAllBits routine sets all bits in a given bitmap variable.
old-location: kernel\rtlsetallbits.htm
old-project: kernel
ms.assetid: a379a910-4712-4d77-af52-614a1b9cc511
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, B, R, RtlSetAllBits, RtlSetAllBits routine [Kernel-Mode Driver Architecture], S, e, i, k109_e7f7eecf-e845-455b-a94d-eccad1ce448a.xml, kernel.rtlsetallbits, l, s, t, wdm/RtlSetAllBits"
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL (See Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlSetAllBits
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlSetAllBits function


## -description


The <b>RtlSetAllBits</b> routine sets all bits in a given bitmap variable. 


## -syntax


````
VOID RtlSetAllBits(
  _In_ PRTL_BITMAP BitMapHeader
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


## -returns



None




## -remarks



Callers of <b>RtlSetAllBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlSetAllBits</b> can be called at any IRQL.




## -see-also

<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindclearbitsandset.md">RtlFindClearBitsAndSet</a>



<a href="..\wdm\nf-wdm-rtlfindlastbackwardrunclear.md">RtlFindLastBackwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlsetbits.md">RtlSetBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlarebitsset.md">RtlAreBitsSet</a>



<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>



<a href="..\wdm\nf-wdm-rtlfindclearruns.md">RtlFindClearRuns</a>



<a href="..\wdm\nf-wdm-rtlnumberofsetbits.md">RtlNumberOfSetBits</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



<a href="..\wdm\nf-wdm-rtlfindnextforwardrunclear.md">RtlFindNextForwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlSetAllBits routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

