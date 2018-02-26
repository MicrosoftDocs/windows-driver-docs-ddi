---
UID: NF:wdm.RtlFindClearRuns
title: RtlFindClearRuns function
author: windows-driver-content
description: The RtlFindClearRuns routine finds the specified number of runs of clear bits within a given bitmap.
old-location: kernel\rtlfindclearruns.htm
old-project: kernel
ms.assetid: ad44c7ba-1d8e-4ba4-8d1b-83ff8b2e3d06
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , C, F, R, RtlFindClearRuns, RtlFindClearRuns routine [Kernel-Mode Driver Architecture], a, d, e, i, k109_10c01954-483b-4ec8-a54d-50928663dc16.xml, kernel.rtlfindclearruns, l, n, r, s, t, u, wdm/RtlFindClearRuns"
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
-	RtlFindClearRuns
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFindClearRuns function


## -description


The <b>RtlFindClearRuns</b> routine finds the specified number of runs of clear bits within a given bitmap.


## -syntax


````
ULONG RtlFindClearRuns(
  _In_  PRTL_BITMAP     BitMapHeader,
  _Out_ PRTL_BITMAP_RUN RunArray,
  _In_  ULONG           SizeOfRunArray,
  _In_  BOOLEAN         LocateLongestRuns
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


### -param RunArray [out]

Pointer to the first element in a caller-allocated array for the bit position and length of each clear run found in the given bitmap variable. 


### -param SizeOfRunArray [in]

Specifies the maximum number of clear runs to satisfy this request.


### -param LocateLongestRuns [in]

If <b>TRUE</b>, specifies that the routine is to search the entire bitmap for the longest clear runs it can find. Otherwise, the routine stops searching when it has found the number of clear runs specified by <i>SizeOfRunArray</i>. 


## -returns



<b>RtlFindClearRuns</b> returns the number of clear runs found.




## -remarks



If <i>LocateLongestRuns </i>is <b>TRUE</b>, the clear runs indicated at <i>RunArray </i>are sorted from longest to shortest. A clear run can consist of a single bit.

Callers of <b>RtlFindClearRuns</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindClearRuns</b> can be called at any IRQL.




## -see-also

<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindlastbackwardrunclear.md">RtlFindLastBackwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="..\wdm\nf-wdm-rtlfindnextforwardrunclear.md">RtlFindNextForwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindClearRuns routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

