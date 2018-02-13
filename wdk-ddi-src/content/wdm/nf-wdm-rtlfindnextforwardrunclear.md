---
UID: NF:wdm.RtlFindNextForwardRunClear
title: RtlFindNextForwardRunClear function
author: windows-driver-content
description: The RtlFindNextForwardRunClear routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position.
old-location: kernel\rtlfindnextforwardrunclear.htm
old-project: kernel
ms.assetid: d923c1a4-4715-4632-8c75-0e48dda9a210
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlFindNextForwardRunClear routine [Kernel-Mode Driver Architecture], wdm/RtlFindNextForwardRunClear, k109_3625ede2-f1b5-495d-9b79-2063e0daa567.xml, RtlFindNextForwardRunClear, kernel.rtlfindnextforwardrunclear
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
-	RtlFindNextForwardRunClear
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFindNextForwardRunClear function


## -description


The <b>RtlFindNextForwardRunClear</b> routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position. 


## -syntax


````
ULONG RtlFindNextForwardRunClear(
  _In_  PRTL_BITMAP BitMapHeader,
  _In_  ULONG       FromIndex,
  _Out_ PULONG      StartingRunIndex
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


### -param FromIndex [in]

Specifies a zero-based bit position at which to start looking for a clear run of bits.


### -param StartingRunIndex [out]

Pointer to a variable in which the starting index of the clear run found in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the run. Its value is meaningless if <b>RtlFindNextForwardRunClear</b> cannot find a run of clear bits. 


## -returns



<b>RtlFindNextForwardRunClear</b> returns either the number of bits in the run beginning at <i>StartingRunIndex</i>, or zero if it cannot find a run of clear bits following <i>FromIndex</i> in the bitmap.




## -remarks



Callers of <b>RtlFindNextForwardRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindNextForwardRunClear</b> can be called at any IRQL.




## -see-also

<a href="..\wdm\nf-wdm-rtlfindlastbackwardrunclear.md">RtlFindLastBackwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindclearruns.md">RtlFindClearRuns</a>



<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>



<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindNextForwardRunClear routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

