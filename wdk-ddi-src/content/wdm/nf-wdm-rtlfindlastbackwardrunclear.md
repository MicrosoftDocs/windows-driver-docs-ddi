---
UID: NF:wdm.RtlFindLastBackwardRunClear
title: RtlFindLastBackwardRunClear function
author: windows-driver-content
description: The RtlFindLastBackwardRunClear routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position.
old-location: kernel\rtlfindlastbackwardrunclear.htm
old-project: kernel
ms.assetid: ad1a6c18-b0c5-4289-9eec-2b8c8d8d2f07
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , B, C, F, L, R, RtlFindLastBackwardRunClear, RtlFindLastBackwardRunClear routine [Kernel-Mode Driver Architecture], a, c, d, e, i, k, k109_b7075a86-ffa4-4a6a-98fb-60848c037253.xml, kernel.rtlfindlastbackwardrunclear, l, n, r, s, t, u, w, wdm/RtlFindLastBackwardRunClear"
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
req.irql: "<= APC_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlFindLastBackwardRunClear
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFindLastBackwardRunClear function


## -description


The <b>RtlFindLastBackwardRunClear</b> routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position.


## -syntax


````
ULONG RtlFindLastBackwardRunClear(
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

Pointer to a variable in which the starting index of the clear run found in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the run preceding the given <i>FromIndex</i>. Its value is meaningless if <b>RtlFindLastBackwardRunClear</b> cannot find a run of clear bits. 


## -returns



<b>RtlFindLastBackwardRunClear</b> returns the number of bits in the run beginning at <i>StartingRunIndex</i>, or zero if it cannot find a run of clear bits preceding <i>FromIndex</i> in the bitmap.




## -remarks



On checked builds of Windows Vista and earlier versions of Windows, the internal implementation of the <b>RtlFindLastBackwardRunClear</b> routine can fail a bogus assertion if the caller is running at IRQL = DISPATCH_LEVEL. The failure of this assertion is harmless and can safely be ignored.

Callers of <b>RtlFindLastBackwardRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindLastBackwardRunClear</b> can be called at any IRQL. 




## -see-also

<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindlastbackwardrunclear.md">RtlFindLastBackwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="..\wdm\nf-wdm-rtlfindnextforwardrunclear.md">RtlFindNextForwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>



<a href="..\wdm\nf-wdm-rtlfindclearruns.md">RtlFindClearRuns</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindLastBackwardRunClear routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

